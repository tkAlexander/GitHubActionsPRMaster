This document provides guidelines for contributing to the repository and deploying changes to various environments.

## Table of Contents

1. [Contributing](#contributing)
    - [Branching Model](#branching-model)
    - [Making Changes](#making-changes)
    - [Pull Requests](#pull-requests)
2. [Deployment](#deployment)
    - [Deployment Environments](#deployment-environments)
    - [Deployment Process](#deployment-process)

## Contributing

### Branching Model

This project follows a Git branching model based on the Gitflow Workflow. The main branches are:

- **master**: Represents the latest stable version of the project. Production-ready changes are merged into this branch.
- **feature/**: Branches created for developing new features or fixing specific issues. Each feature or fix should have its own feature branch.

### Making Changes

To contribute to the project, follow these steps:

1. Clone the repository: `git clone <repository-url>`
2. Create a new feature branch from `develop`: `git checkout -b feature/<feature-name>`
3. Make changes and commit them to your feature branch: `git commit -am "Brief description of changes"`
4. Push your feature branch to the remote repository: `git push origin feature/<feature-name>`
5. Open a pull request targeting the `master` branch.
6. Discuss and review changes with team members.
7. After approval, merge your pull request into `master`.

### Pull Requests

When opening a pull request:

- Provide a descriptive title and detailed description of the changes.
- Reference relevant issues or feature requests if applicable.
- Ensure the code passes all tests and follows coding standards.
- Request reviews from team members.

## Deployment

### Deployment Environments

The docker images are deployed to multiple environments for testing and production use:

- **Development**: Used for testing new features and changes. Deployed automatically from the `feature` branch.
- **Test**: Pre-production environment for final testing before release. Deployed from release candidates on the `master` branch.
- **Production**: Live environment accessible to end-users. Deployed from the `master` branch.

### Deployment Process

To deploy changes to different environments:

1. **Development**: Open pull request from `feature` into `develop` branch trigger automatic deployment to the development environment.
2. **Test**: Once testing in development is complete and approved, merge the `release` branch into `master` and deploy to the test environment.
3. **Production**: Deployment to production environment is manually triggered from the `master` branch.
