# Contributing to AMBASSADORS SMS

First off, thank you for considering contributing to the Ambassadors Educational Complex School Management System! It's people like you that make this project such a great tool for Cameroon's education sector.

## 📋 Table of Contents

- [Code of Conduct](#code-of-conduct)
- [How Can I Contribute?](#how-can-i-contribute)
- [Development Setup](#development-setup)
- [Git Workflow](#git-workflow)
- [Coding Standards](#coding-standards)
- [Commit Messages](#commit-messages)
- [Pull Request Process](#pull-request-process)
- [Code Review Guidelines](#code-review-guidelines)
- [Reporting Issues](#reporting-issues)
- [Feature Requests](#feature-requests)
- [Questions](#questions)

## 🤝 Code of Conduct

This project and everyone participating in it is governed by a Code of Conduct. By participating, you are expected to uphold this code.

### Our Standards

Examples of behavior that contributes to creating a positive environment include:
- Using welcoming and inclusive language
- Being respectful of differing opinions, viewpoints, and experiences
- Gracefully accepting constructive criticism
- Focusing on what is best for the community
- Showing empathy towards other community members

Examples of unacceptable behavior include:
- The use of sexualized language or imagery and unwelcome sexual attention or advances
- Trolling, insulting/derogatory comments, and personal or political attacks
- Public or private harassment
- Publishing others' private information without explicit permission
- Other conduct which could reasonably be considered inappropriate

## 🎯 How Can I Contribute?

### Reporting Bugs 🐛

Before creating bug reports, please check the issue list as you might find out that you don't need to create one. When you are creating a bug report, please include as many details as possible:

**Template for Bug Reports:**
```markdown
**Describe the bug:**
A clear and concise description of what the bug is.

**To Reproduce:**
Steps to reproduce the behavior:
1. Go to '...'
2. Click on '....'
3. See error

**Expected behavior:**
A clear and concise description of what you expected to happen.

**Screenshots:**
If applicable, add screenshots showing the problem.

**Environment:**
- Browser: [e.g., Chrome 90, Firefox 88]
- OS: [e.g., Windows 10, macOS 11, Ubuntu 20.04]
- System Specs: [RAM, Processor if relevant]

**Additional context:**
Add any other context about the problem here.
```

### Feature Requests 💡

Enhancement suggestions are tracked as GitHub issues. When creating an enhancement suggestion, please include:

**Template for Feature Requests:**
```markdown
**Is your feature request related to a problem?**
A clear and concise description of what the problem is.

**Describe the solution you'd like:**
A clear and concise description of what you want to happen.

**Describe alternatives you've considered:**
A clear and concise description of any alternative solutions or features you've considered.

**Additional context:**
Add any other context or screenshots about the feature request here.
```

### Code Contributions 💻

You can contribute code in the following ways:
- Add new features
- Fix bugs
- Improve documentation
- Optimize performance
- Enhance UI/UX
- Add test cases

## 🔧 Development Setup

### Prerequisites
- Git installed on your machine
- A GitHub account
- A text editor or IDE (VS Code recommended)
- Basic knowledge of HTML, CSS, and JavaScript

### Step-by-Step Setup

1. **Fork the Repository**
   ```bash
   # Visit https://github.com/yourusername/ambassadors-sms
   # Click the "Fork" button in the top right
   ```

2. **Clone Your Fork**
   ```bash
   git clone https://github.com/yourusername/ambassadors-sms.git
   cd ambassadors-sms
   ```

3. **Add Upstream Remote**
   ```bash
   git remote add upstream https://github.com/original/ambassadors-sms.git
   git remote -v  # Verify both origin and upstream are listed
   ```

4. **Create a Feature Branch**
   ```bash
   git checkout -b feature/your-feature-name
   ```

5. **Make Your Changes**
   - Edit the necessary files
   - Test your changes in the browser
   - Keep changes focused on a single feature

6. **Keep Your Fork Updated**
   ```bash
   git fetch upstream
   git rebase upstream/main
   ```

## 📚 Git Workflow

### Branch Naming Convention

Please use descriptive branch names:
```
feature/add-student-portal          # New feature
bugfix/fix-attendance-calculation   # Bug fix
docs/update-readme                  # Documentation
style/improve-sidebar-design        # UI improvements
refactor/optimize-salary-module     # Code refactoring
test/add-attendance-tests           # Adding tests
```

### Commit Workflow

1. Make changes to your feature branch
2. Test thoroughly
3. Commit with clear messages
4. Push to your fork
5. Create a Pull Request

## 📝 Coding Standards

### HTML Standards
```html
<!-- Use semantic HTML5 elements -->
<section>
    <h2>Heading</h2>
    <p>Content</p>
</section>

<!-- Use proper indentation (2 spaces) -->
<!-- Use meaningful class names -->
<!-- Add comments for complex sections -->
```

### CSS Standards
```css
/* Use CSS variables for colors */
:root {
    --primary-color: #0091da;
    --text-color: #1a1a1a;
}

/* Use descriptive class names */
.student-attendance-table { }
.form-input-field { }

/* Organize by sections */
/* HEADER */
/* SIDEBAR */
/* MAIN CONTENT */
/* FOOTER */

/* Use proper indentation */
/* Keep specificity low */
```

### JavaScript Standards
```javascript
// Use camelCase for variables and functions
const studentName = "John Doe";
function markAttendance() { }

// Use meaningful variable names
const attendancePercentage = 95;
const isAbsent = false;

// Add comments for complex logic
// Calculate salary with 1% deduction per absent day
const deduction = baseSalary * (0.01 * absentDays);

// Use const and let, avoid var
const immutableValue = 100;
let mutableValue = 50;

// Proper function documentation
/**
 * Calculates the final salary after absence deductions
 * @param {number} baseSalary - The base salary amount
 * @param {number} absentDays - Number of absent days
 * @returns {number} Final adjusted salary
 */
function calculateFinalSalary(baseSalary, absentDays) {
    return baseSalary - (baseSalary * 0.01 * absentDays);
}
```

### Formatting
- Use 2 spaces for indentation
- Max line length: 100 characters (where reasonable)
- No trailing whitespace
- One blank line between sections
- Use single quotes in JavaScript

## 💬 Commit Messages

Write clear, concise commit messages:

```bash
# Good commit messages
git commit -m "Add student enrollment form"
git commit -m "Fix salary calculation for absence deductions"
git commit -m "Update attendance marking UI"
git commit -m "Refactor fee management module"

# Bad commit messages
git commit -m "fix bug"
git commit -m "update"
git commit -m "changes"
```

### Commit Message Format
```
[Type] Brief description (50 chars max)

Detailed explanation if needed (72 chars max per line)

- Point 1
- Point 2
```

### Commit Types
- `feat:` A new feature
- `fix:` A bug fix
- `docs:` Documentation changes
- `style:` Formatting, missing semicolons, etc.
- `refactor:` Code refactoring
- `perf:` Performance improvements
- `test:` Adding or updating tests

### Examples
```bash
git commit -m "feat: Add student dashboard with KPI cards"
git commit -m "fix: Correct attendance percentage calculation"
git commit -m "docs: Update installation guide"
git commit -m "style: Format salary table styling"
git commit -m "refactor: Simplify modal management code"
git commit -m "perf: Optimize report generation"
```

## 🔄 Pull Request Process

### Before Submitting a PR
1. ✅ Test your changes thoroughly
2. ✅ Update documentation if needed
3. ✅ Check for merge conflicts with main branch
4. ✅ Ensure your code follows the style guide
5. ✅ Keep the number of commits reasonable

### Creating a Pull Request

1. **Push to Your Fork**
   ```bash
   git push origin feature/your-feature-name
   ```

2. **Open a Pull Request**
   - Visit your fork on GitHub
   - Click "Compare & pull request"
   - Fill in the PR template

3. **PR Title Format**
   ```
   [Module] Brief description
   
   Examples:
   [Attendance] Add monthly summary view
   [Salaries] Fix absence deduction calculation
   [UI] Improve sidebar navigation styling
   ```

4. **PR Description Template**
   ```markdown
   ## Description
   Briefly describe your changes and why they're needed.

   ## Type of Change
   - [ ] Bug fix (non-breaking change)
   - [ ] New feature (non-breaking change)
   - [ ] Breaking change
   - [ ] Documentation update

   ## Related Issues
   Closes #(issue number)

   ## Testing Done
   - [ ] Tested in Chrome
   - [ ] Tested in Firefox
   - [ ] Tested on mobile
   - [ ] Manual testing completed

   ## Screenshots (if applicable)
   Add screenshots of the changes.

   ## Checklist
   - [ ] My code follows the style guide
   - [ ] I have updated documentation
   - [ ] No new warnings generated
   - [ ] I have tested my changes
   - [ ] Changes are breaking or not
   ```

## 👀 Code Review Guidelines

### For Authors (when your PR is being reviewed)
- Be open to feedback
- Respond to comments professionally
- Make requested changes promptly
- Ask questions if unclear

### For Reviewers (when reviewing others' PRs)
- Be respectful and constructive
- Praise good code
- Suggest improvements politely
- Test the changes if possible
- Approve when satisfied

## 📌 Reporting Issues

### Security Issues
If you find a security vulnerability, please email `security@ambassadorseducational.cm` instead of using the issue tracker.

### Bug Reports
1. Check if the bug already exists
2. Create a new issue
3. Use the bug report template
4. Include all requested information
5. Be specific and provide reproduction steps

### Enhancement Requests
1. Check if the feature already exists
2. Create a new issue
3. Use the feature request template
4. Explain the use case
5. Suggest implementation if possible

## ❓ Questions

For questions about contributing:
1. Check the existing documentation
2. Look at closed issues and PRs
3. Post in GitHub Discussions
4. Email: dev@ambassadorseducational.cm

---

## 🎉 Recognition

Contributors will be recognized in:
- The CONTRIBUTORS.md file
- Release notes
- GitHub contributors page

## 📖 Additional Resources

- [Git Documentation](https://git-scm.com/doc)
- [GitHub Guides](https://guides.github.com/)
- [How to Write Good Commit Messages](https://chris.beams.io/posts/git-commit/)
- [Semantic Versioning](https://semver.org/)

---

Thank you for your contributions! 🙏

**Happy coding!** ✨
