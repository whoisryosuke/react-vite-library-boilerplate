# React Vite Library Boilerplate

Create code libraries using React, Typescript, and Vite to automatically release to NPM.

For example, you could create a component library for a design system (so someone can `import { ComponentName } from 'your-custom-library'`).

## Getting Started

### Preview the code

1. Clone this project: `git clone git@github.com:whoisryosuke/react-vite-library-boilerplate.git`
1. Install dependencies: `yarn`
1. Start the dev server: `yarn dev`

Open the app in your web browser: http://localhost:5174/

### Write code

Write code in `src/` and export any components, functions, etc in the `index.ts`.

### Release

Releases are automated by GitHub Actions and the [`release-please` library/CLI](https://github.com/googleapis/release-please). See [the workflow for more details](.github\workflows\release-please.yml).

1. Make commits that follow [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) guidelines: `yarn commit`
1. Push to `main` branch on GitHub to trigger release.
1. GitHub Action checks if new version needs to be released based on commit history, bumps version, then creates new release on NPM.

> If you want to copy this setup, make sure to enable Actions creating and approving pull requests, and a `NPM_TOKEN` repository secret.
