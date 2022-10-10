<!-- markdownlint-disable MD041 -->

<!-- PROJECT SHIELDS -->
[![gh-ci][gh-ci-shield]][gh-ci-url]
[![pre-commit][pre-commit-shield]][pre-commit-url]
[![renovate][renovate-shield]][renovate-dashboard-url]
[![license][license-shield]][license-url]

# STRG. helm charts

A collection of charts we use in our projects.

<!-- GETTING STARTED -->

## Getting Started

### Prerequisites

- [Helm 3][helm-url] installed, please check the [official documentation][helm-docu-url].

### pre-commit

To use pre-commit ensure that all dependencies are installed locally.

### helm-docs

To install helm-docs follow-up steps in https://github.com/norwoodj/helm-docs#installation
Docs are generating documentation like README in each chart module.
To generate or regenerate it locally you can call (you can see also logs)

```bash
helm-docs
```

or call (it will validate all files not just changes)

```bash
pre-commit run --all-files
```

<!-- USAGE EXAMPLES -->

## Usage

```console
helm repo add gh-strg https://strg-at.github.io/charts/
```

## Test template

Go to module dir f.e. charts/agents-graphql-api

```bash
helm dependency build
```

Test all templates for module

```bash
helm template agents-graphql-api .
```

If you need to define some values you can do it with additional file, that will be set on top of values.yaml

```bash
helm template agents-graphql-api . --values test-values.yaml
```

Example of test-values for agents-graphql-api

```yaml
config:
  app:
    # -- The application port where it will be acessible
    port: "0"
    # -- host for graphql
    host: "1"

  authService:
    # -- base url for authentication service
    baseUrl: "2"
```

<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->

[pre-commit-url]: https://github.com/pre-commit/pre-commit
[pre-commit-shield]: https://img.shields.io/badge/pre--commit-enabled-brightgreen?logo=pre-commit&style=for-the-badge
[renovate-dashboard-url]: https://app.renovatebot.com/dashboard
[renovate-shield]: https://img.shields.io/badge/renovate-enabled-brightgreen?logo=renovatebot&style=for-the-badge
[gh-ci-shield]: https://img.shields.io/github/workflow/status/strg-at/charts/On%20Push%20%7C%20Release%20Charts?event=push&label=chart-releaser&logo=github&style=for-the-badge
[gh-ci-url]: https://github.com/strg-at/charts/actions/workflows/helm-release.yaml
[helm-url]: https://helm.sh
[helm-docu-url]: https://helm.sh/docs/
[license-shield]: https://img.shields.io/github/license/strg-at/charts?color=brightgreen&label=%E2%9A%96%EF%B8%8F%20license&style=for-the-badge
[license-url]: https://github.com/strg-at/charts/blob/main/LICENSE
