# Agent Compass

**A comprehensive set of rules and guidelines for AI-assisted development in Cursor IDE**

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Language](https://img.shields.io/badge/language-English-green.svg)
![Platform](https://img.shields.io/badge/platform-Cursor%20IDE-purple.svg)

## Overview

Agent Compass is not just another AI prompt - it's a complete **Policy Framework for AI-Assisted Development**. Think of it as a "Constitution" for your AI coding assistant that transforms it from a simple code generator into a disciplined, professional developer who follows best practices, security standards, and architectural principles.

### What Makes Agent Compass Special?

-   **📋 Structured Reporting**: Get detailed reports on what was changed, what couldn't be completed, and what requires manual attention
-   **🏗️ Architect-Developer Role Model**: Clear separation of responsibilities between you (the architect) and the AI (the developer)
-   **🔒 Security-First Approach**: Built-in security guidelines and sensitive data handling protocols
-   **📝 Smart Commenting Standards**: Enforces Better Comments style and A-temporal documentation
-   **🎯 Proactive Evaluation**: AI evaluates your technical approaches and suggests alternatives when appropriate
-   **🔧 Language-Specific Guidelines**: Tailored rules for Python, JavaScript, TypeScript, C#, C++, and PowerShell

## Who Is This For?

-   **Cursor IDE Users** who want consistent, high-quality AI-generated code
-   **Software Architects** who need to delegate coding tasks while maintaining standards
-   **Development Teams** looking to standardize AI-assisted development practices
-   **Anyone** frustrated with unpredictable AI code quality

## Installation

### For Cursor IDE

1. Open Cursor IDE
2. Press `Ctrl+Shift+P` (or `Cmd+Shift+P` on Mac)
3. Type "Cursor: Configure User Rules" and select it
4. Copy the contents of [`COMPASS.md`](./COMPASS.md) from this repository
5. Paste the content into the rules editor
6. Save and close

### Verification

After installation, start a new chat with your AI assistant and give it a coding task. You should notice:

-   More structured responses
-   Better code quality
-   Detailed reports at the end of each interaction
-   Consistent commenting and documentation

## Key Features

### 🎯 Role-Based Interaction

The AI operates as your "Developer" while you remain the "Software Architect", creating a clear hierarchy and responsibility structure.

### 📊 Structured Output Format

Every AI response ends with a comprehensive report including:

-   **Changes Made**: List of all modifications implemented
-   **Unfulfilled Tasks**: Any tasks that couldn't be completed
-   **Manual Changes Required**: Operations requiring your intervention
-   **Special Attention Required**: Critical aspects needing review
-   **Rationale for Deviations**: Explanations for significant design decisions

### 🔐 Security & Best Practices

-   Never embeds sensitive information in code
-   Uses clear, conventional placeholders
-   Provides security recommendations
-   Enforces proper error handling and input validation

### 📝 Professional Documentation

-   Enforces Better Comments style (`*` Important, `!` Warning, `?` Question, `TODO:` Future plans)
-   Requires English-only comments and documentation
-   Mandates A-temporal, declarative commenting (describes what code _does_, not what it _used to do_)

## Usage Examples

### Basic Task Assignment

```
You: "Create a user authentication system with JWT tokens"

AI Response: [Implements the system with proper structure]

Changes Made:
- Created AuthService class with JWT token generation
- Implemented user login/logout endpoints
- Added input validation and error handling
- Created middleware for token verification

Manual Changes Required:
- Replace JWT_SECRET_KEY placeholder with actual secret
- Configure database connection string
- Add authentication routes to main router

Special Attention Required:
- Review JWT expiration time (currently set to 24 hours)
- Verify password hashing salt rounds meet security requirements
```

### Complex Architecture Discussion

```
You: "I think we should use microservices for this project"

AI Response: I'll evaluate this architectural approach for your specific context.

[Provides implementation]

Rationale for Significant Deviations:
While microservices offer scalability benefits, for a team of 2-3 developers with moderate traffic expectations, a well-structured monolith with clear module boundaries might be more appropriate. This approach provides:
- Simpler deployment and debugging
- Reduced operational complexity
- Easier transaction management
- Lower infrastructure costs

However, if you anticipate rapid scaling or have specific service isolation requirements, I can proceed with the microservices approach.
```

## Language-Specific Features

### Python

-   Google Python Style Guide compliance
-   Google Style Docstrings
-   Automatic `tqdm` integration for progress bars

### JavaScript/TypeScript

-   Airbnb Style Guide adherence
-   JSDoc/TSDoc documentation
-   TypeScript Deep Dive Guide compliance

### C#

-   Microsoft C# Coding Conventions
-   XML Documentation Comments for public APIs

### C++

-   ISO C++ Core Guidelines compliance
-   Doxygen-style comments

### PowerShell

-   Safe string concatenation with `-f` operator
-   Proper error handling patterns

## Part of the Agent Tools Ecosystem

Agent Compass is part of the larger **Artemonim's Agent Tools** ecosystem:

-   **[Agent Docstrings](https://github.com/Artemonim/AgentDocstrings)** - Helps AI understand your codebase structure
-   **Agent Enforcer** _(Coming Soon)_ - Automated code quality verification
-   **Agent Viewport** _(Coming Soon)_ - UI markup understanding for AI assistants

## Contributing

We welcome contributions! Please see our [Contributing Guidelines](./CONTRIBUTING.md) for details.

## License

This project is licensed under the MIT License - see the [LICENSE](./LICENSE) file for details.

## Support

If you find Agent Compass helpful, please ⭐ star this repository and share it with other developers!

For questions, issues, or suggestions, please open an issue in this repository.

---

**Made with ❤️ by [Artemonim](https://github.com/Artemonim)**
