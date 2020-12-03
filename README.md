# charts-example

## Prerequisites

- Unix-like OS
- [chart-releaser](https://github.com/helm/chart-releaser) installed and available on the path as `helm-cr`. The recommended way to install chart-releaser is to use ASDF. `asdf plugin-add helm-cr https://github.com/Antiarchitect/asdf-helm-cr.git`
- [pre-commit](https://pre-commit.com/)
- [go-task](https://taskfile.dev)

## Getting Started

1. Fork/import this repository
1. Delete the fake charts and add your real ones
1. Follow the [Usage](#usage) section for details on how to package and deliver charts

## Usage

```sh
# Validate everything to make sure nothing is screwed up
task validate

# Run tests
task test

# Package, push, and release new changes
export CR_TOKEN='abc123abc123abc123abc123abc123abc123'
export CR_OWNER='my-org'
export CR_GIT_REPO='my-cool-repo'
export CR_CHARTS_REPO='https://my-org.github.io/my-cool-repo'
task deliver

# Just package
task chart-releaser:package

# Just push
task chart-releaser:upload

# Just release
task chart-releaser:indexAndPush
```

## Notes

1. This project does not support signing charts at this time. It is something we are looking into doing in the future. Please let us know if creating signed charts is something you can't live without.
