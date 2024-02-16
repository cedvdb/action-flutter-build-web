
# See also

  - [flutter build android](https://github.com/cedvdb/action-flutter-build-android)
  - [flutter build ios](https://github.com/cedvdb/action-flutter-build-ios)

# Usage

```
name: Build and distribute

on:
  push:
    branches:
      - main

jobs:
  build:
    name: build
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2

      - uses: cedvdb/action-flutter-build-web@v1
        with:
          build-cmd: flutter build web --release
          working-directory: ./

      - name: Archive Production artifact
        uses: actions/upload-artifact@v2
        with:
          name: release
          path: build/web
```
