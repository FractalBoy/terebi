# Repository Guidelines

## Project Structure & Module Organization

This is a BrightScript/SceneGraph Roku client for Dispatcharr recordings. Application metadata is in `src/manifest`. The startup entry point is `src/source/main.bs`. SceneGraph UI components live in `src/components/`, with each component normally represented by a matching PascalCase `.xml` layout and `.bs` controller, such as `MainScene.xml` and `MainScene.bs`. Add image assets under `src/images/` when needed. Generated `build/` and dependency `node_modules/` directories are ignored.

## Build, Test, and Development Commands

- `npm ci` installs the locked development dependencies for a clean checkout.
- `npm run build` removes prior `build/` and `out/` output, then compiles the project using `bsconfig.json`. The configured `@rokucommunity/bslint` plugin reports lint diagnostics during compilation.

There is currently no `test` script, test directory, CI workflow, or documented deployment command. Validate UI and playback changes on a Roku development device after a successful build; describe the device scenario exercised in the pull request.

## Coding Style & Naming Conventions

Follow the existing BrightScript style: four-space indentation, lowercase BrightScript keywords (`sub`, `function`, `if`, `end if`), and one statement per line. Use PascalCase for SceneGraph component file names and component names (`GetRecordingsTask`); pair its `.xml` and `.bs` files. Use descriptive camelCase for functions, fields, and local variables (`returnToMainScene`, `serverUrlField`). Keep component behavior in its controller and declare scene/UI structure in XML. Preserve the existing formatter’s output if formatting files with `brighterscript-formatter`.

## Testing Guidelines

For every change, run `npm run build` before submitting. Add focused automated tests and an `npm test` script when introducing testable non-UI logic; name tests after the feature or behavior they cover. For SceneGraph interactions, manually check focus navigation, Back/OK behavior, sign-in validation, and recording playback as applicable.

## Commit & Pull Request Guidelines

The available history uses brief imperative commit subjects (for example, `Add license file`). Keep subjects concise and action-oriented; make each commit a coherent change. Pull requests should explain the user-visible behavior, list validation performed, link any relevant issue, and include screenshots or a short video for UI changes. Do not commit credentials, server URLs containing secrets, build artifacts, or `node_modules/`.
