# C3 compiler setup

## Options

```yaml
inputs:
  os:
    description: The operating system target (e.g. linux, macos, windows)
    default: (auto-detected)
  arch:
    description: The CPU architecture (e.g. x64, arm64)
    default: (auto-detected)
  version:
    description: The compiler version to install
    default: latest
  build-type:
    description: The build type (release or debug)
    default: release
```

## Example configuration

### Basic

```yaml
name: Build

on:
  pull_request:

jobs:
  build:
    name: Build project
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v6
      - uses: ManuLinares/setup-c3
      - run: c3c compile myproject
```

### Custom Version & Build Type

```yaml
    steps:
      - uses: actions/checkout@v6
      - uses: ManuLinares/setup-c3
        with:
          version: nightly
          build-type: debug
      - run: c3c compile myproject
```
