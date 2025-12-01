# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is the BizSKY政企信息化脚手架系统2025版 (BizSKY Government-Enterprise Informationization Scaffolding System 2025 Edition). The project is currently in early development stage with a basic repository structure initialized.

## Repository Structure

The repository currently contains minimal files:
- `README.md` - Basic project description in Chinese
- `LICENSE` - Apache License 2.0
- `.gitignore` - Java-focused git ignore file (suggests Java technology stack)
- Git configuration pointing to `git@github.com:SimonBizsky/BizSKY.git`

## Technology Stack Indicators

Based on the `.gitignore` file, this project appears to be targeting a Java technology stack:
- Java class files and build artifacts (*.class, *.jar, *.war, *.ear)
- Maven/Gradle build files (package files section)
- Java IDE configurations (BlueJ, Mobile Tools for Java)
- JVM crash logs and error files

## Development Setup

Currently, there are no build configuration files (package.json, pom.xml, build.gradle, etc.) present in the repository. As the project develops, expect to add:

1. **Build System Configuration** - Likely Maven (pom.xml) or Gradle (build.gradle) based on Java stack indicators
2. **Project Structure** - Standard Java project directory structure (src/main/java, src/test/java, etc.)
3. **Dependencies** - Java dependencies for government-enterprise informationization systems

## License

The project is licensed under Apache License 2.0, which allows for commercial use, modification, distribution, and private use, with the requirement to include the original copyright and license notice.

## Git Configuration

- Remote origin: `git@github.com:SimonBizsky/BizSKY.git`
- Default branch: `main`
- Git LFS is configured for the repository

## Notes for Future Development

This is a scaffolding system project, which typically includes:
- Project templates and boilerplate code
- Build automation and CI/CD pipelines
- Standardized directory structures
- Common utilities and libraries
- Configuration management
- Documentation and examples

As the project grows, update this CLAUDE.md file with specific build commands, testing procedures, and architectural patterns that emerge.