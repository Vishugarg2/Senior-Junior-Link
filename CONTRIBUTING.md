# Contributing to ConnectPro

Thank you for your interest in contributing to ConnectPro! This document provides guidelines and information for contributors.

## 🚀 Getting Started

### Prerequisites
- Node.js (version 18 or higher)
- npm or yarn package manager
- Git for version control
- Basic knowledge of React, TypeScript, and Express.js

### Setting Up Development Environment

1. **Fork and Clone**
```bash
git clone https://github.com/yourusername/connectpro.git
cd connectpro
```

2. **Install Dependencies**
```bash
npm install
```

3. **Start Development Server**
```bash
npm run dev
```

4. **Verify Setup**
- Open `http://localhost:5000`
- Check that profiles load and search works
- Test profile creation modal

## 📋 Development Guidelines

### Code Style
- **TypeScript**: All new code must be written in TypeScript
- **ESLint**: Follow the existing ESLint configuration
- **Formatting**: Use Prettier for consistent code formatting
- **Naming**: Use descriptive variable and function names

### Component Guidelines
- **Functional Components**: Use React functional components with hooks
- **Props Interface**: Define TypeScript interfaces for all component props
- **File Structure**: One component per file, named exports preferred
- **Styling**: Use Tailwind CSS classes, avoid inline styles

### API Guidelines
- **RESTful Design**: Follow REST conventions for new endpoints
- **Validation**: Use Zod schemas for all input validation
- **Error Handling**: Implement proper error responses with meaningful messages
- **TypeScript**: Maintain full type safety in API layer

## 🔧 Project Structure

```
├── client/src/
│   ├── components/        # Reusable UI components
│   │   ├── ui/           # shadcn/ui components
│   │   └── ...           # Feature components
│   ├── pages/            # Route components
│   ├── lib/              # Utilities and configurations
│   ├── hooks/            # Custom React hooks
│   └── ...
├── server/
│   ├── index.ts          # Server entry point
│   ├── routes.ts         # API route definitions
│   ├── storage.ts        # Data layer
│   └── vite.ts           # Vite configuration
├── shared/
│   └── schema.ts         # Shared TypeScript types
└── ...
```

## 🎯 Types of Contributions

### Bug Fixes
- **Issue First**: Create or find an existing issue describing the bug
- **Minimal Changes**: Keep fixes focused and minimal
- **Test Coverage**: Ensure the fix doesn't break existing functionality
- **Documentation**: Update documentation if the fix affects user behavior

### New Features
- **Discussion**: Open an issue to discuss the feature before implementation
- **Design First**: Consider UI/UX implications of new features
- **Backward Compatibility**: Maintain compatibility with existing API
- **Documentation**: Include documentation updates with new features

### UI/UX Improvements
- **Consistency**: Maintain design consistency with existing components
- **Accessibility**: Ensure new UI elements are accessible
- **Responsive Design**: Test on multiple screen sizes
- **User Testing**: Consider user impact of design changes

### Documentation
- **Clarity**: Write clear, concise documentation
- **Examples**: Include code examples where helpful
- **Screenshots**: Update screenshots for UI changes
- **Accuracy**: Ensure documentation matches current implementation

## 📝 Pull Request Process

### Before Submitting
1. **Branch Naming**: Use descriptive branch names (e.g., `feature/profile-editing`, `fix/search-bug`)
2. **Code Quality**: Run ESLint and fix any issues
3. **Testing**: Test your changes thoroughly
4. **Documentation**: Update relevant documentation

### PR Description Template
```markdown
## Description
Brief description of the changes

## Type of Change
- [ ] Bug fix
- [ ] New feature
- [ ] UI/UX improvement
- [ ] Documentation update
- [ ] Performance improvement

## Testing
- [ ] Tested on desktop
- [ ] Tested on mobile
- [ ] Tested edge cases
- [ ] No console errors

## Screenshots (if applicable)
Include screenshots for UI changes

## Additional Notes
Any additional information for reviewers
```

### Review Process
1. **Automatic Checks**: Ensure all CI checks pass
2. **Code Review**: Address reviewer feedback promptly
3. **Testing**: Reviewers will test functionality
4. **Approval**: Minimum one approval required for merge

## 🐛 Bug Reports

### Before Reporting
- **Search**: Check if the bug has already been reported
- **Reproduce**: Ensure you can consistently reproduce the issue
- **Environment**: Note your browser, OS, and device details

### Bug Report Template
```markdown
## Bug Description
Clear description of what the bug is

## Steps to Reproduce
1. Go to '...'
2. Click on '...'
3. Scroll down to '...'
4. See error

## Expected Behavior
What you expected to happen

## Actual Behavior
What actually happened

## Screenshots
If applicable, add screenshots

## Environment
- OS: [e.g. iOS]
- Browser: [e.g. Chrome, Safari]
- Version: [e.g. 22]
- Device: [e.g. iPhone6]
```

## 💡 Feature Requests

### Before Requesting
- **Search**: Check if the feature has been requested
- **Use Case**: Consider the broader use case
- **Alternatives**: Consider existing solutions or workarounds

### Feature Request Template
```markdown
## Feature Summary
Brief summary of the requested feature

## Problem Statement
What problem does this solve?

## Proposed Solution
Detailed description of the proposed feature

## Alternative Solutions
Other solutions you've considered

## Additional Context
Any other context or screenshots
```

## 🔍 Code Review Guidelines

### For Contributors
- **Self Review**: Review your own code before submitting
- **Small PRs**: Keep pull requests focused and reasonably sized
- **Clear Commits**: Write clear, descriptive commit messages
- **Responsive**: Respond to review feedback promptly

### For Reviewers
- **Constructive**: Provide constructive, helpful feedback
- **Explain**: Explain the reasoning behind suggestions
- **Timely**: Review PRs in a timely manner
- **Thorough**: Test the changes when possible

## 📚 Resources

### Documentation
- [React Documentation](https://reactjs.org/docs)
- [TypeScript Handbook](https://www.typescriptlang.org/docs/)
- [Tailwind CSS Documentation](https://tailwindcss.com/docs)
- [shadcn/ui Documentation](https://ui.shadcn.com/)

### Tools
- [Vite Documentation](https://vitejs.dev/guide/)
- [Drizzle ORM Documentation](https://orm.drizzle.team/)
- [TanStack Query Documentation](https://tanstack.com/query/latest)

## 🤝 Code of Conduct

### Our Standards
- **Respectful**: Treat all contributors with respect
- **Inclusive**: Welcome contributions from everyone
- **Constructive**: Provide helpful, constructive feedback
- **Professional**: Maintain professional communication

### Enforcement
- **Issues**: Report problematic behavior to maintainers
- **Consequences**: Violations may result in temporary or permanent bans
- **Appeals**: Appeal process available for disputed decisions

## 📞 Getting Help

### Discord Community
Join our Discord server for real-time discussions and help.

### GitHub Discussions
Use GitHub Discussions for:
- General questions
- Feature discussions
- Best practices
- Community showcase

### Issue Tracker
Use GitHub Issues for:
- Bug reports
- Feature requests
- Documentation issues

---

Thank you for contributing to ConnectPro! Your contributions help make professional networking more accessible and effective for everyone.