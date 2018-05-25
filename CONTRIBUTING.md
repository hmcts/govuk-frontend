# Contributing

We're not ready for contributions yet, this document exists as a guide for those working on govuk-frontend.

## Code of Conduct
Please read [CODE_OF_CONDUCT.md](./CODE_OF_CONDUCT.md) before contributing.

## Running locally

You'll need [Git](https://help.github.com/articles/set-up-git/) and [Node.js](https://nodejs.org/en/) installed to get this project running.

Note: You will need the Node.js version specified in the [.nvmrc](./.nvmrc) file.
This should reflect the most current [active LTS (Long-term support)](https://github.com/nodejs/Release#release-schedule).

### 1. Fork repository (optional)
If you're an external contributor make sure to [fork this project first](https://help.github.com/articles/fork-a-repo/)

### 2. Clone repository
```
git clone git@github.com:alphagov/govuk-frontend.git # or clone your own fork

cd govuk-frontend
```

### 3. Using nvm (optional)
If you work across multiple Node.js projects there's a good chance they require different Node.js and npm versions.

To enable this we use [nvm (Node Version Manager)](https://github.com/creationix/nvm) to switch between versions easily.

1. [install nvm](https://github.com/creationix/nvm#installation)
2. Run `nvm install` in the project directory (this will use [.nvmrc](./.nvmrc))

### 4. Install npm dependencies
We use [npm](https://docs.npmjs.com/getting-started/what-is-npm) to manage the dependencies in development.
```
npm install
```

### 5. Start a local server
This will build sources, serve pages and watch for changes.
```
npm start
```

## Deploying

See [deploying](/docs/contributing/deploying).

## Application architecture

See [application architecture](/docs/contributing/application-architecture.md) for an overview of the directories in this repository.

## Conventions to follow

### Indentation and whitespace

2-space, soft-tabs only. No trailing whitespace.

### CSS

Prefix all classes with `.govuk-`.

Use the BEM naming convention.

For more detail, see our [coding standards for CSS](/docs/coding-standards/css.md).

### JavaScript

`govuk-frontend` uses [standardjs](http://standardjs.com/), an opinionated JavaScript linter.
All JavaScript files follow its conventions, and it runs on CI to ensure that new pull requests are in line with them.

To check the whole codebase, run:

    npm test

For more detail, see our [coding standards for JavaScript](/docs/coding-standards/js.md).

If you need polyfills for features that are not yet included in this project, please see the following guide on [how to add polyfills](/docs/contributing/polyfilling.md).

### Components and Nunjucks API

Find components in `src/components`.

See our [coding standards for components](/docs/coding-standards/components.md) and [coding standards for Nunjucks macros](/docs/coding-standards/nunjucks-api.md).

### Component folder structure and naming

Component folder and files should be singular, except in cases where they are more commonly used in groups, for example, radios, breadcrumbs and checkboxes.

An example component exists in `src/components/component-example`.

Use this as the basis for creating new components.

The folder structure should be:

    component-name
      - `_component-name.scss`
      - `component-name.html`
      - `component-name.js`
      - `README.md`


### Testing components on their own
You can run a subset of the test suite that only tests components by running:

    npm run test:components

Note: There's a watch mode that keeps a testing session open waiting for changes that can be used with:

    npm run test:components -- --watch

#### Updating component snapshots

If a snapshot test fails, review the difference in the console. If the change is the correct change to make, run:

`npm run test:components -- -u`

This will update the snapshot file. Commit this file separately with a commit message that explains you're updating the snapshot file and an explanation of what caused the change.

## Browser support
Your contribution needs to work with certain browsers as set out in [README](../../README.md). See also [supporting Internet Explorer 8](../installation/supporting-internet-explorer-8.md).

## Application tasks

See [tasks](/docs/contributing/tasks.md).

## Updating Changelog

If you open a GitHub pull request on this repo, please update `CHANGELOG` to reflect your contribution.

Add your entry under `Unreleased` as `Breaking change`, `New feature`, `Fix` or `Internal`.

Please include a description of the work done and a link to the PR (see current `CHANGELOG` for the format).

Include the modified `CHANGELOG` in the PR.


## Versioning

We are not using semantic versioning yet, we are going to talk about this soon.

See `CHANGELOG` for more information.

## Releasing a new version

See [publishing](publishing.md).

## Commit hygiene

Please see our [git style guide](https://github.com/alphagov/styleguides/blob/master/git.md)
which describes how we prefer git history and commit messages to read.
