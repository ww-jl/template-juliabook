# Jupyter book template for Julia Jupyter notebooks

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/sosiristseng/template-juliabook/main)

Click `Use this template` button to copy this repository to your account.

## Jupyter Book

[Jupyter book](https://jupyterbook.org/index.html) creates a beautiful website from Markdown and Jupyter Notebook files.

## CI/CD

When changes are pushed to GitHub, continuous integration/deployment (CI/CD) will build the notebooks and publish the website. Execution results are executed on the fly so you can push notebooks with empty output cells and obtain the execution results generated by the CI service.

### GitHub actions

To enable GitHub pages for the generated website:
Open your repository settings => Pages => GitHub Pages
=> Build and deployment => Source, Select `GitHub actions`

### Cirrus CI

Related files for [Cirrus CI](https://cirrus-ci.org/) workflow
- [.cirrus.yml](.cirrus.yml)
- [cirrus-notify.yml](.github/workflows/cirrus-notify.yml)

To enable GitHub pages for the generated website:
Open your repository settings => Pages => GitHub Pages
=> Build and deployment => Source, Select the `gh-pages` branch.

## Auto update Julia dependencies

See [update-manifest.yml](.github/workflows/update-manifest.yml).

This template repository periodically updates Julia dependent packages and make a PR if the notebooks are executed successfully with the updated packages.

[See the instructions](https://github.com/peter-evans/create-pull-request/blob/main/docs/concepts-guidelines.md#triggering-further-workflow-runs) for how to trigger CI workflows in a PR. In this repo, I use a custom [GitHub APP](https://github.com/peter-evans/create-pull-request/blob/main/docs/concepts-guidelines.md#authenticating-with-github-app-generated-tokens) to generate a temporary token.
