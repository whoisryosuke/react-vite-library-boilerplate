# React Vite Library Boilerplate

Create code libraries using React, Typescript, and Vite to automatically release to NPM.

For example, you could create a component library for a design system (so someone can `import { ComponentName } from 'your-custom-library'`).

## Getting Started

### Preview the code

1. Clone this project: `git clone git@github.com:whoisryosuke/react-vite-library-boilerplate.git`
1. Install dependencies: `yarn`
1. Start the dev server: `yarn dev`

Open the app in your web browser: http://localhost:5174/

> You can also install libraries like Storybook to preview UI components. [See `oat-milk-design` for reference.](https://github.com/whoisryosuke/oat-milk-design)

### Write code

Write code in `src/` and export any components, functions, etc in the `index.ts`.

**Tips:**

- **Installing a package?** If you don't want to include it in the bundle, install it as a peer dependency and add it to the `vite.config.js` file and the `build.rollupOptions.external` array. You can see we do this with React - since we expect the user to bring their own copy.

### Release

**First time setup**:

1. Edit the `package.json` and change `name` to your module's name (`anything-dash-separated`). Then find and replace the old name with the new name (like the `main` or `module` properties).
1. Go to [the project settings](https://github.com/whoisryosuke/react-vite-library-boilerplate/settings/actions) and allow Read/Write access for Actions (Settings > Code and Automation > Actions > General - the Workflow permissions part of the page)
1. Add your [`NPM_TOKEN`](https://www.npmjs.com/settings/your-username/tokens) as [a repository secret](https://github.com/whoisryosuke/react-vite-library-boilerplate/settings/secrets/actions) for Actions. Make sure it's a **"Granular access token"** - the legacy type requires a one-time password (which doesn't work with this workflow).

**Using GitHub:**

1. Run the new version GitHub action. _This updates your `package.json` with the new version and creates a new tag on GitHub._
1. Create a new release with the new version tag. _This triggers a build that automatically gets pushed to NPM._

**Or manually:**

1. Bump version in `package.json`
1. `yarn build`
1. `npm publish`
1. Create new tag and release on GitHub.
