# Contributing to EEG Workshop

Thank you for your interest in contributing! This document provides guidelines for contributing to the EEG Workshop project.

## How to Contribute

### 1. Reporting Issues

If you find a bug or have a suggestion:

1. Check if the issue already exists
2. Create a new issue with:
   - Clear title
   - Detailed description
   - Steps to reproduce (for bugs)
   - Expected vs actual behavior
   - Your environment (Python version, OS, etc.)

### 2. Suggesting Enhancements

We welcome ideas for:
- New analysis methods
- Additional visualizations
- Better explanations
- More example datasets
- Performance improvements

### 3. Code Contributions

#### Getting Started

1. Fork the repository
2. Clone your fork:
   ```bash
   git clone https://github.com/YOUR-USERNAME/EEG-Workshop.git
   cd EEG-Workshop
   ```

3. Create a branch:
   ```bash
   git checkout -b feature/your-feature-name
   ```

#### Making Changes

1. **Follow the style**:
   - Add detailed comments explaining WHY, not just WHAT
   - Use clear variable names
   - Include docstrings for functions

2. **Test your changes**:
   - Run all notebook cells
   - Verify outputs are correct
   - Check that explanations are clear

3. **Document**:
   - Update README if needed
   - Add comments to new code
   - Explain parameter choices

#### Submitting Changes

1. Commit your changes:
   ```bash
   git add .
   git commit -m "Add: brief description of changes"
   ```

2. Push to your fork:
   ```bash
   git push origin feature/your-feature-name
   ```

3. Create a Pull Request:
   - Clear title and description
   - Reference any related issues
   - Explain what changed and why

## Code Style

### Python Code

- Follow PEP 8 guidelines
- Use meaningful variable names
- Add type hints where helpful
- Keep functions focused and small

### Comments

- Explain WHY, not just WHAT
- Include parameter reasoning
- Mention trade-offs and alternatives
- Use clear, educational language

### Notebooks

- Clear markdown explanations
- Logical cell organization
- Outputs visible (don't clear)
- Progressive difficulty

## Areas for Contribution

### High Priority

- [ ] Additional example datasets
- [ ] More visualization types
- [ ] Statistical analysis methods
- [ ] Artifact detection algorithms
- [ ] Time-frequency analysis

### Medium Priority

- [ ] Performance optimizations
- [ ] Additional language translations
- [ ] Video tutorials
- [ ] Interactive widgets
- [ ] Automated testing

### Low Priority

- [ ] Alternative filter implementations
- [ ] GUI for parameter selection
- [ ] Export to other formats
- [ ] Integration with other tools

## Questions?

Feel free to:
- Open an issue for discussion
- Start a GitHub Discussion
- Contact the maintainers

## Code of Conduct

- Be respectful and inclusive
- Provide constructive feedback
- Help others learn
- Celebrate contributions

Thank you for helping make EEG analysis more accessible! 🧠✨
