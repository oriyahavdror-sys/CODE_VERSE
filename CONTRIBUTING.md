# Contributing to CODE VERSE

First off, thank you for considering contributing to CODE VERSE! 🎉

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [How Can I Contribute?](#how-can-i-contribute)
- [Development Process](#development-process)
- [Style Guidelines](#style-guidelines)
- [Adding New Missions](#adding-new-missions)
- [Translation Guidelines](#translation-guidelines)

---

## Code of Conduct

This project and everyone participating in it is governed by our Code of Conduct. By participating, you are expected to uphold this code.

### Our Standards

- Be respectful and inclusive
- Welcome newcomers
- Focus on what is best for the community
- Show empathy towards other community members

---

## How Can I Contribute?

### 🐛 Reporting Bugs

Before creating bug reports, please check existing issues. When creating a bug report, include:

- Clear and descriptive title
- Exact steps to reproduce
- Expected vs actual behavior
- Screenshots if applicable
- Your environment (browser, OS, etc.)

### 💡 Suggesting Features

Feature suggestions are welcome! Please:

- Use a clear and descriptive title
- Provide detailed description of the feature
- Explain why this feature would be useful
- Include mockups or examples if possible

### 🎯 Adding Missions

We always need more learning content! See [Adding New Missions](#adding-new-missions) below.

### 🌍 Translations

Help us reach more people by improving or adding translations! See [Translation Guidelines](#translation-guidelines).

### 📝 Improving Documentation

Documentation improvements are always appreciated:

- Fix typos or clarify existing docs
- Add examples
- Improve README files
- Write tutorials or guides

---

## Development Process

### 1. Fork & Clone

```bash
# Fork the repo on GitHub, then:
git clone https://github.com/YOUR-USERNAME/code-verse.git
cd code-verse
```

### 2. Create a Branch

```bash
git checkout -b feature/your-feature-name
# or
git checkout -b fix/bug-description
```

### 3. Install Dependencies

```bash
npm install
```

### 4. Make Your Changes

- Follow the style guidelines below
- Test your changes thoroughly
- Update documentation if needed

### 5. Commit Your Changes

```bash
git add .
git commit -m "feat: add new cryptography mission"
# or
git commit -m "fix: resolve XSS validation issue"
```

**Commit Message Format:**
- `feat:` New feature
- `fix:` Bug fix
- `docs:` Documentation changes
- `style:` Formatting changes
- `refactor:` Code refactoring
- `test:` Adding tests
- `chore:` Maintenance tasks

### 6. Push & Create PR

```bash
git push origin feature/your-feature-name
```

Then create a Pull Request on GitHub with:
- Clear title and description
- Reference any related issues
- Screenshots/GIFs if applicable

---

## Style Guidelines

### JavaScript/React

- Use functional components with hooks
- Follow existing code structure
- Add comments for complex logic
- Use meaningful variable names

### Tailwind CSS

- Use Tailwind utility classes
- Follow responsive design patterns (mobile-first)
- Maintain consistency with existing styles

### Code Example

```javascript
// Good ✅
const handleMissionComplete = async (missionId) => {
  const newXP = player.xp + mission.xpReward;
  const newLevel = Math.floor(newXP / 500) + 1;
  
  await savePlayerData({
    ...player,
    xp: newXP,
    level: newLevel
  });
};

// Avoid ❌
const handleMissionComplete = async (m) => {
  const x = player.xp + mission.xpReward;
  await savePlayerData({...player, xp: x, level: Math.floor(x / 500) + 1});
};
```

---

## Adding New Missions

### Mission Structure

```javascript
{
  id: 6,
  title: {
    he: 'כותרת בעברית',
    en: 'Title in English',
    ar: 'عنوان بالعربية'
  },
  difficulty: 'beginner', // 'beginner', 'intermediate', 'advanced'
  specialization: 'web-security', // 'web-security', 'crypto', 'offensive'
  xpReward: 100,
  coinReward: 50,
  description: {
    he: 'תיאור המשימה',
    en: 'Mission description',
    ar: 'وصف المهمة'
  },
  instructions: 'Detailed HTML instructions...',
  challenge: {
    question: 'What is the challenge?',
    hint: 'A helpful hint',
    solution: 'Expected solution code',
    validation: (userCode) => {
      // Return true if correct
      return userCode.includes('expectedPattern');
    }
  },
  explanation: 'What the user should learn from this mission',
  practiceQuestion: {
    question: { he: '', en: '', ar: '' },
    solution: 'Practice solution code'
  }
}
```

### Mission Guidelines

1. **Difficulty Levels**
   - **Beginner**: Assume zero knowledge, explain everything
   - **Intermediate**: Basic concepts known, introduce new techniques
   - **Advanced**: Complex scenarios, professional-level concepts

2. **Instructions Should Include**
   - Clear explanation of the concept
   - Real-world examples
   - Code examples with comments
   - Security implications

3. **Validation**
   - Check for correct patterns, not exact code
   - Allow multiple valid solutions
   - Provide meaningful error messages

4. **Explanations**
   - Explain why this is important
   - Show real-world applications
   - Link to related concepts

---

## Translation Guidelines

### Languages Supported

- Hebrew (עברית) - he
- English - en
- Arabic (العربية) - ar

### Translation Rules

1. **Consistency**: Use consistent terminology across all missions
2. **Cultural Sensitivity**: Adapt examples to be culturally appropriate
3. **RTL Support**: Ensure proper text direction for Hebrew/Arabic
4. **Terminology**: Maintain a glossary of technical terms

### Adding a Translation

1. Find the translation object in the code
2. Add your translation for the new language
3. Ensure all UI elements are translated
4. Test RTL layout if applicable

Example:

```javascript
const translations = {
  he: {
    mission: {
      start: 'התחל משימה',
      // ...
    }
  },
  en: {
    mission: {
      start: 'Start Mission',
      // ...
    }
  },
  ar: {
    mission: {
      start: 'ابدأ المهمة',
      // ...
    }
  }
};
```

---

## Testing

Before submitting your PR:

- [ ] Test in Chrome, Firefox, and Safari
- [ ] Test on mobile devices
- [ ] Test all three languages
- [ ] Test RTL layout (Hebrew/Arabic)
- [ ] Verify responsive design
- [ ] Check for console errors

---

## Questions?

Feel free to:
- Open an issue with the `question` label
- Join our Discord community
- Email the maintainers

---

## Recognition

Contributors will be:
- Listed in README.md
- Mentioned in release notes
- Part of the project's history

Thank you for making CODE VERSE better! 🚀
