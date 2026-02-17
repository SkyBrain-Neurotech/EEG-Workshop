# 🚀 Quick Start Guide

Get up and running with EEG signal processing in 5 minutes!

## Step 1: Install Python

If you don't have Python installed:
- Download from [python.org](https://www.python.org/downloads/)
- Version 3.7 or higher required
- Make sure to check "Add Python to PATH" during installation

## Step 2: Clone Repository

```bash
git clone https://github.com/SkyBrain-Neurotech/EEG-Workshop.git
cd EEG-Workshop
```

## Step 3: Install Dependencies

### Option A: Using pip (Recommended)

```bash
pip install -r requirements.txt
```

### Option B: Using conda

```bash
conda create -n eeg-workshop python=3.9
conda activate eeg-workshop
pip install -r requirements.txt
```

## Step 4: Launch Jupyter

```bash
jupyter notebook
```

This will open your browser automatically.

## Step 5: Open the Notebook

1. In the Jupyter interface, click on `chords_web_experiment.ipynb`
2. Read the introduction
3. Run the first cell (Shift + Enter)
4. Continue through the notebook

## 📖 What to Expect

### Cell 1: Configuration
- Sets up all parameters
- Explains why each value was chosen
- **Action**: Just run it, read the comments

### Cell 2: Load Data
- Reads the CSV file
- Converts to proper units
- **Action**: Run and observe the statistics

### Cell 3: Visualize Raw Data
- Shows what unfiltered EEG looks like
- **Action**: Look for noise and artifacts

### Cell 4-6: Filtering
- Cleans the signal step by step
- **Action**: Compare before/after plots

### Cell 7-8: Frequency Analysis
- Analyzes brain wave frequencies
- **Action**: Identify dominant frequency bands

## 🎯 Learning Tips

1. **Read Comments First**: Every parameter has a "WHY" explanation
2. **Run Sequentially**: Don't skip cells
3. **Experiment**: Try changing parameters after first run
4. **Compare**: Look at before/after visualizations
5. **Ask Questions**: Use GitHub Issues if stuck

## 🔧 Common Issues

### "Module not found"
```bash
pip install <module-name>
```

### "Jupyter not found"
```bash
pip install jupyter
```

### "CSV file not found"
Make sure you're in the EEG-Workshop directory:
```bash
cd EEG-Workshop
jupyter notebook
```

### Plots not showing
Add this to the first cell:
```python
%matplotlib inline
```

## 📊 Expected Results

After running all cells, you should see:

1. ✅ Raw EEG signal plot (noisy)
2. ✅ Filtered EEG signal plot (clean)
3. ✅ Power spectral density plot
4. ✅ Frequency band power values
5. ✅ Before/after comparison

## 🎓 Next Steps

After completing `chords_web_experiment.ipynb`:

1. **Experiment**: Modify filter parameters
2. **Your Data**: Try with your own EEG files
3. **Advanced**: Open `Complete_EEG_Workshop.ipynb`
4. **Share**: Star the repo and share with others!

## 💡 Pro Tips

- **Save Often**: File → Save and Checkpoint
- **Restart Kernel**: If something breaks, Kernel → Restart & Clear Output
- **Export**: File → Download as → HTML (to share results)
- **Learn More**: Read COMMENTS_SUMMARY.md for detailed explanations

## 🆘 Need Help?

- **Documentation**: Read README.md
- **Issues**: [GitHub Issues](https://github.com/SkyBrain-Neurotech/EEG-Workshop/issues)
- **Discussions**: [GitHub Discussions](https://github.com/SkyBrain-Neurotech/EEG-Workshop/discussions)

## ⏱️ Time Estimates

- **Setup**: 5 minutes
- **First Run**: 10 minutes
- **Understanding**: 30 minutes
- **Experimentation**: 1+ hours
- **Mastery**: Keep practicing!

---

**Ready? Let's process some brain waves! 🧠✨**

```bash
jupyter notebook chords_web_experiment.ipynb
```
