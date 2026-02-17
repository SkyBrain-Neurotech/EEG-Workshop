# Comments Added to chords_web_experiment.ipynb

## Summary of Changes

I've added comprehensive "WHY WE CHOSE" comments throughout the notebook explaining every parameter choice and design decision.

## What Was Added

### 1. Configuration Parameters (Step 1)

**SAMPLING_RATE = 500 Hz**
- WHY 500 Hz?
  - Nyquist theorem requires 2× highest frequency
  - Brain signals go up to ~100 Hz (gamma)
  - 500 Hz captures up to 250 Hz cleanly
  - Standard in research EEG (clinical: 256 Hz, research: 500-1000 Hz)
  - Good balance between data quality and file size

**CONVERSION_FACTOR = 1000**
- WHY 1000?
  - Raw data is in millivolts (mV)
  - EEG measured in microvolts (µV) by convention
  - 1 mV = 1000 µV
  - Typical EEG amplitude: 10-100 µV

**HIGHPASS_CUTOFF = 4.0 Hz**
- WHY 4 Hz?
  - Removes slow drifts and DC offset (< 4 Hz)
  - Preserves theta (4-8 Hz) and above
  - Trade-off: loses delta band (0.5-4 Hz)
  - Chosen because we focus on theta/alpha/beta/gamma
  - Common choices: 0.1 Hz (conservative), 1 Hz (standard), 4 Hz (aggressive)

**LOWPASS_CUTOFF = 45.0 Hz**
- WHY 45 Hz?
  - Keeps full gamma band (30-45 Hz)
  - Removes muscle artifacts (>50 Hz)
  - Stays below line noise (50 Hz)
  - Muscle EMG is typically 50-200 Hz
  - Common choices: 30 Hz (conservative), 40 Hz (standard), 50 Hz (permissive)

**NOTCH_FREQ = 50.0 Hz**
- WHY 50 Hz?
  - Electrical line noise from AC power
  - 50 Hz in Europe/Asia/Africa/Australia
  - 60 Hz in Americas
  - Pure artifact, not brain activity
  - Also removes harmonics (100 Hz, 150 Hz, etc.)

**FILTER_ORDER = 4**
- WHY Order 4?
  - Higher order = sharper cutoff, more ringing
  - Lower order = gentler cutoff, less distortion
  - Order 4 = good compromise (24 dB/octave)
  - Standard in EEG research
  - Butterworth filter: -24 dB/octave rolloff

### 2. Frequency Bands

**Delta (0.5-4 Hz)**
- WHY? Deep sleep, unconscious processes, high amplitude slow waves
- Dominant during deep sleep (stages 3-4)

**Theta (4-8 Hz)**
- WHY? Drowsiness, meditation, memory consolidation, creativity
- Light sleep, hippocampal activity during navigation

**Alpha (8-13 Hz)**
- WHY? Relaxed wakefulness, eyes closed, 'idling' brain rhythm
- Strongest in occipital cortex
- Disappears when eyes open

**Beta (13-30 Hz)**
- WHY? Active thinking, concentration, anxiety, motor activity
- Associated with alertness and problem-solving

**Gamma (30-45 Hz)**
- WHY? High-level cognition, sensory binding, consciousness
- Attention, working memory, perception

### 3. Data Loading (Step 2)

**Using .values**
- WHY? Converts pandas Series to numpy array for faster processing
- Required by scipy.signal functions

**Multiplying by CONVERSION_FACTOR**
- WHY? Raw data in mV, we need µV (standard EEG unit)
- Makes values easier to interpret (10-100 µV range)

**Creating time axis**
- WHY? Converts sample numbers to seconds
- Example: sample 500 at 500 Hz = 1.0 second
- Makes plots more interpretable

### 4. Filter Design

**Butterworth Filter**
- WHY Butterworth?
  - Maximally flat passband (no ripples)
  - Smooth frequency response
  - Most common in EEG research
  - Good balance between sharpness and artifacts
- Alternatives: Chebyshev (sharper but ripples), Bessel (better phase)

**Nyquist Frequency**
- WHY 0.5 × sampling rate?
  - Can only represent frequencies up to fs/2 (Nyquist theorem)
  - At 500 Hz sampling, max frequency is 250 Hz

**Normalization**
- WHY normalize? scipy requires frequencies in [0,1]
- 1.0 = Nyquist frequency

**filtfilt vs lfilter**
- WHY filtfilt?
  - Zero phase distortion (no time shift)
  - Applies filter forward then backward
  - Doubles effective order (4 → 8)
  - Essential for EEG timing accuracy

### 5. Notch Filter

**Quality Factor Q=30**
- WHY Q=30?
  - Q = center_freq / bandwidth
  - Q=30 means bandwidth ≈ 50/30 ≈ 1.67 Hz
  - Removes 50 Hz ± 0.8 Hz
  - Higher Q = narrower (more selective)
  - Standard range: 20-50

**IIR vs FIR**
- WHY IIR?
  - More efficient for notch filters
  - Requires fewer coefficients
  - Sharp notch with minimal computation

### 6. Visualization

**Figure Size (15, 4)**
- WHY figsize=(15,4)?
  - Width 15: Shows enough time to see patterns
  - Height 4: Compact but readable
  - 4:1 aspect ratio emphasizes time dimension
  - Good for time-series data

**Duration = 10 seconds**
- WHY 10 seconds?
  - Long enough to see rhythms (alpha completes 80-130 cycles)
  - Short enough to see individual waveforms
  - Good balance for visual inspection

**Line Width = 0.5**
- WHY 0.5?
  - Thin lines show detail without clutter
  - At 500 Hz, we have 5000 points in 10 seconds
  - Default (1.0) too thick for high-frequency data

**Grid Alpha = 0.3**
- WHY alpha=0.3?
  - Makes grid subtle, not distracting
  - Helps read values without overwhelming the data

## Educational Value

These comments help users understand:
1. **The reasoning** behind each choice
2. **Trade-offs** involved in parameter selection
3. **Alternatives** and why they weren't chosen
4. **Standards** in EEG research
5. **Practical implications** of each decision

## Result

The notebook is now a comprehensive educational resource that not only shows HOW to process EEG data, but explains WHY each step is done the way it is.
