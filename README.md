# 🧠 EEG Signal Processing Workshop

A comprehensive, educational workshop for learning EEG (Electroencephalography) signal processing from scratch. This repository contains hands-on Jupyter notebooks with detailed explanations of every step, parameter choice, and processing decision.

## 📚 What You'll Learn

- **EEG Fundamentals**: Understanding brain waves and their frequencies
- **Signal Preprocessing**: Filtering techniques to clean raw EEG data
- **Frequency Analysis**: Power spectral density and frequency band analysis
- **Practical Implementation**: Reusable Python code for your own projects
- **Best Practices**: Industry-standard parameters and methods

## 🎯 Who Is This For?

- Neuroscience students and researchers
- Data scientists interested in biosignals
- Engineers working with EEG devices
- Anyone curious about brain signal processing

**Prerequisites**: Basic Python knowledge, familiarity with numpy and matplotlib

## 📁 Repository Contents

### Notebooks

1. **`chords_web_experiment.ipynb`** ⭐ **START HERE**
   - Step-by-step EEG processing tutorial
   - Real data from ChordsWeb EEG device
   - Detailed "WHY WE CHOSE" comments explaining every parameter
   - Covers: filtering, frequency analysis, visualization
   - **Best for**: Beginners and practical learning

2. **`Complete_EEG_Workshop.ipynb`**
   - Comprehensive EEG analysis workshop
   - Advanced techniques and methods
   - Multiple analysis approaches
   - **Best for**: In-depth understanding

### Data

- **`ChordsWeb-20251111-193931.csv`**
  - Real EEG recording from ChordsWeb device
  - Single channel data
  - Sampling rate: 500 Hz
  - Duration: ~524 seconds

### Documentation

- **`COMMENTS_SUMMARY.md`**: Detailed explanation of all parameter choices
- **`README.md`**: This file

## 🚀 Quick Start

### 1. Clone the Repository

```bash
git clone https://github.com/SkyBrain-Neurotech/EEG-Workshop.git
cd EEG-Workshop
```

### 2. Install Dependencies

```bash
pip install -r requirements.txt
```

Or install manually:

```bash
pip install numpy pandas matplotlib scipy jupyter
```

### 3. Launch Jupyter Notebook

```bash
jupyter notebook
```

### 4. Open and Run

1. Start with `chords_web_experiment.ipynb`
2. Read the comments carefully - they explain WHY each choice was made
3. Run cells sequentially (Shift + Enter)
4. Experiment with parameters to see their effects

## 📊 What's Inside the Notebooks?

### Step 1: Configuration
- **Sampling Rate**: 500 Hz (why this matters)
- **Filter Settings**: High-pass (4 Hz), Low-pass (45 Hz), Notch (50 Hz)
- **Frequency Bands**: Delta, Theta, Alpha, Beta, Gamma

### Step 2: Data Loading
- Reading CSV files
- Converting units (mV → µV)
- Creating time axis

### Step 3: Visualization
- Plotting raw EEG signals
- Understanding what to look for
- Identifying artifacts

### Step 4: Filtering
- **High-Pass Filter** (4 Hz): Removes slow drifts
- **Low-Pass Filter** (45 Hz): Removes muscle artifacts
- **Notch Filter** (50 Hz): Removes electrical line noise

### Step 5: Frequency Analysis
- Power Spectral Density (PSD)
- Frequency band power calculation
- Interpreting results

## 🎓 Key Concepts Explained

### Why These Filter Settings?

**High-Pass at 4 Hz**
- ✅ Removes slow drifts and DC offset
- ✅ Preserves theta, alpha, beta, gamma bands
- ⚠️ Trade-off: Loses delta band (0.5-4 Hz)

**Low-Pass at 45 Hz**
- ✅ Keeps full gamma band (30-45 Hz)
- ✅ Removes muscle artifacts (>50 Hz)
- ✅ Stays below line noise frequency

**Notch at 50 Hz**
- ✅ Removes electrical interference
- ✅ Narrow bandwidth (~1.67 Hz)
- 📍 Use 60 Hz for North America

### Frequency Bands & Mental States

| Band | Frequency | Mental State |
|------|-----------|--------------|
| **Delta** | 0.5-4 Hz | Deep sleep, unconscious |
| **Theta** | 4-8 Hz | Drowsiness, meditation, memory |
| **Alpha** | 8-13 Hz | Relaxed, eyes closed |
| **Beta** | 13-30 Hz | Active thinking, concentration |
| **Gamma** | 30-45 Hz | High-level cognition |

## 🔧 Customization

### Using Your Own Data

1. Replace `ChordsWeb-20251111-193931.csv` with your CSV file
2. Update these parameters in Step 1:

```python
CSV_FILE = 'your_file.csv'
CHANNEL_NAME = 'your_channel_name'
SAMPLING_RATE = 500.0  # Your sampling rate
```

### Adjusting Filter Settings

```python
# More aggressive drift removal
HIGHPASS_CUTOFF = 1.0  # Hz (keeps delta band)

# More conservative noise removal
LOWPASS_CUTOFF = 30.0  # Hz (removes gamma band)

# North America line noise
NOTCH_FREQ = 60.0  # Hz
```

## 📖 Learning Path

### Beginner
1. Read the notebook markdown cells
2. Run each code cell
3. Observe the outputs
4. Read the "WHY WE CHOSE" comments

### Intermediate
1. Modify parameters and observe changes
2. Try different filter settings
3. Analyze your own EEG data
4. Compare before/after filtering

### Advanced
1. Implement additional analysis methods
2. Add time-frequency analysis
3. Perform statistical comparisons
4. Build automated pipelines

## 🛠️ Technical Details

### Dependencies

- **Python**: 3.7+
- **NumPy**: Array operations and numerical computing
- **Pandas**: Data loading and manipulation
- **Matplotlib**: Visualization
- **SciPy**: Signal processing (filters, FFT)
- **Jupyter**: Interactive notebooks

### Filter Implementation

- **Type**: Butterworth (maximally flat passband)
- **Order**: 4 (24 dB/octave rolloff)
- **Method**: `filtfilt` (zero-phase filtering)
- **Quality Factor**: 30 (for notch filter)

## 📝 Best Practices

1. **Always visualize** raw data before processing
2. **Document parameters** - future you will thank you
3. **Save intermediate results** for comparison
4. **Validate filtering** - check frequency response
5. **Report settings** in publications

## 🤝 Contributing

We welcome contributions! Please:

1. Fork the repository
2. Create a feature branch
3. Add your improvements
4. Submit a pull request

Ideas for contributions:
- Additional analysis methods
- More example datasets
- Translations
- Bug fixes
- Documentation improvements

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🙏 Acknowledgments

- **ChordsWeb**: EEG device used for data collection
- **SkyBrain Neurotech**: Workshop development and maintenance
- **MNE-Python**: Inspiration for EEG processing standards
- **Neuroscience Community**: For established best practices

## 📧 Contact

- **Issues**: [GitHub Issues](https://github.com/SkyBrain-Neurotech/EEG-Workshop/issues)
- **Discussions**: [GitHub Discussions](https://github.com/SkyBrain-Neurotech/EEG-Workshop/discussions)
- **Website**: [SkyBrain Neurotech](https://skybrain-neurotech.com)

## 🌟 Star This Repository

If you find this workshop helpful, please ⭐ star this repository to help others discover it!

## 📚 Additional Resources

### Books
- "Analyzing Neural Time Series Data" by Mike X Cohen
- "EEG Signal Processing" by Saeid Sanei

### Online Courses
- MNE-Python Tutorials
- Coursera: Computational Neuroscience

### Papers
- Delorme & Makeig (2004): EEGLAB - EEG processing toolbox
- Widmann et al. (2015): Digital filter design for EEG

---

**Happy Learning! 🧠✨**

*Last Updated: February 2025*
