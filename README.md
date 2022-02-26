# Custom Styled Components Library w/Typescript

## Getting Started

Simply run the commands below and you _should_ have a working storybook displaying all of our components.

- `git clone repo`
- `yarn install`
- `npm run dev`

## Adding Components

Each component follows the folder structure below:

- ComponentName
    - index.tsx
    - index.stories.tsx
    - styles.ts

### Index.tsx
Exports react component to be consumed

### Stories.tsx
Showcase of component for storybook

### Styles.ts
Exports a styled component consumed by the react component


## Publishing to NPM

When you are ready to publish the package to NPM, use the `release.prepare` script:
```shell
yarn run release.prepare -m "Commit message" --patch
```

This script will increment the version number in `package.json` based on the specified version type (`--patch`, `--minor`, or `--major` are valid switches). The script will also check in the changes, commit the changes, and create a git tag with the new version number.

After the script runs successfully, you will need to push the tag to Github. Once the tag is pushed, Travis CI will run and publish the package to NPM. This process usually takes 1-2 minutes.
```shell
git push origin x.y.z
```
Where x.y.z is the new version number (part of the script output).

Notes:
- If the git commit message is left blank, it will default to "[Release]"
- If the version type is left blank, `patch` will be used by default

