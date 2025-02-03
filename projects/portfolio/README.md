# Minifolio

Minifolio is my home-made content management system for my portfolio site, which I use to showcase my work on a vibrant website.


## Project goals



Minifolio is designed to store your data in a flexible manner, with the full site configuration being a Git repository to allow it to be backed up easily from any system. All the portfolio data files are human-readable, and can be edited without Minifolio's editor (if you desire).


## Developing


I have developed Minifolio with high standards for code quality and correctness. I use TypeScript and ESLint to ensure code quality, with a thorough suite of integration tests to validate its correctness. Additionally, these checks are performed on all pull requests using GitHub Actions for continuous integration.

## Deploying


I self-host Minifolio on my server Ursula, where it runs in a Docker container. The project has many features to allow it to be used securely within Docker. For example, it supports using its own SSH configuration and git configuration, meaning there is no need to pass-through the system SSH.