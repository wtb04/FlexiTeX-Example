<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/wtb04/FlexiTeX/refs/heads/main/misc/FlexiTeX-light.svg">
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/wtb04/FlexiTeX/refs/heads/main/misc/FlexiTeX-dark.svg">
  <img alt="FlexiTeX Logo" height="100">
</picture>

This repository demonstrates collaborative workflows for LaTeX projects using [FlexiTeX](https://github.com/wtb04/FlexiTeX), a command-line tool for restructuring large LaTeX documents.
The example showcases how three collaborators can maintain personalized formatting styles in separate branches — [collaborator-a](https://github.com/wtb04/FlexiTeX-Example/tree/collaborator-a), [collaborator-b](https://github.com/wtb04/FlexiTeX-Example/tree/collaborator-b) and [collaborator-c](https://github.com/wtb04/FlexiTeX-Example/tree/collaborator-c) — while keeping content synchronized through an intermediate representation.

## Overview

The system is built on a two-step GitHub Actions workflow, powered by FlexiTeX:

1. **From Personal to Internal:**  
   When a collaborator pushes to their personal branch, the workflow runs FlexiTeX with no configuration settings to convert the document into a standardized internal format. The output is committed to this branch.
2. **From Internal to Collaborators:**  
   A second workflow is triggered by changes to the internal branch. This workflow reprocesses the internal document using each collaborator’s custom configuration file and distributes the resulting formatted documents to their respective branches.
   Each personal branch includes its own `.config.yml` configuration file defining the desired output style.

### This setup allows:

Personalized formatting for each collaborator
Clean separation between authoring and formatting
Automatic bidirectional sync via the internal format

## License

MIT License. See [LICENSE](LICENSE).
