<div align="center">

  ![StandardRB](https://github.com/andrewmcodes/standardrb-action/workflows/StandardRB/badge.svg)
  ![Tests](https://github.com/andrewmcodes/standardrb-action/workflows/Test/badge.svg)
  ![Build](https://github.com/andrewmcodes/standardrb-action/workflows/Build/badge.svg)
  [![Changelog](https://github.com/andrewmcodes/standardrb-action/workflows/Changelog/badge.svg)](/CHANGELOG.md)
  ![Version Number](https://img.shields.io/static/v1?label=Version&message=v0.0.1&color=blue)
</div>

# :white_check_mark: HAML Lint Action

A GitHub Action to run HAML-Lint against your code and create annotations in the GitHub UI.

- [:white_check_mark: HAML Lint Action](#whitecheckmark-haml-lint-action)
  - [:page_facing_up: Introduction](#pagefacingup-introduction)
  - [:bulb: Usage](#bulb-usage)
    - [:package: Example Workflow](#package-example-workflow)
  - [:warning: Gotchas](#warning-gotchas)
  - [:camera_flash: Screenshots](#cameraflash-screenshots)
  - [:bookmark: Changelog](#bookmark-changelog)
  - [:sos: Contributing](#sos-contributing)
  - [:rotating_light: Code of Conduct](#rotatinglight-code-of-conduct)
  - [:copyright: License](#copyright-license)
  - [:robot: Check Out My Other Ruby GitHub Actions](#robot-check-out-my-other-ruby-github-actions)

## :page_facing_up: Introduction

GitHub Actions are an amazing new tool that can dramatically improve productivity while using the GitHub platform. While it is not hard to write a custom GitHub action to run HAML-Lint on your codebase, this action takes that functionality one step further using the checks API. After the HAML Lint Action runs HAML-Lint against your code, it will create annotations that you can easily view, matched up with the offending code.

Since GitHub actions and the checks API are continually changing, it is possible that there will be breaking API changes that affect this action. If so, please open an issue and I will look into it as soon as I can.

## :bulb: Usage

Add the following to your GitHub action workflow to use HAML Lint Action:

```yaml
- name: HAML Lint
  uses: andrewmcodes/haml-lint-action@v0.0.1
  env:
    GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

### :package: Example Workflow

Here is an example workflow file incorporating HAML Lint Action:

```yaml
name: HAML Lint

on: [push]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v1
    - name: HAML Lint
      uses: andrewmcodes/haml-lint-action@v0.0.1
      env:
        GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

## :warning: Gotchas

Due to the GitHub Check Runs API, we can only return 50 annotations per run. See [here](https://developer.github.com/v3/checks/runs/#output-object) for more info.

## :camera_flash: Screenshots

TODO

## :bookmark: Changelog

[View our Changelog](/CHANGELOG.md)

## :sos: Contributing

[Contributing Guide](/CONTRIBUTING.md)

## :rotating_light: Code of Conduct

[Code of Conduct](/CODE_OF_CONDUCT.md)

## :copyright: License

[MIT](/LICENSE.md)

## :robot: Check Out My Other Ruby GitHub Actions

- [andrewmcodes/rubocop-linter-action](https://github.com/andrewmcodes/rubocop-linter-action).
- [andrewmcodes/standardrb-action](https://github.com/andrewmcodes/standardrb-action).