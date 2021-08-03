# @alexmarqs/commitlint-config

Shareable [`commitlint`](https://github.com/conventional-changelog/commitlint) config used in personal projects.

## How to install

```sh
# Install commitlint-config
npm install -D @alexmarqs/commitlint-config @commitlint/cli
# or
yarn add -D @alexmarqs/commitlint-config @commitlint/cli
```

## Usage

After installing it, apply the config to `commitlint` by running the following command:

```sh
# Note: configuration is picked up from commitlint.config.js, .commitlintrc.js, .commitlintrc.json, or .commitlintrc.yml file or a commitlint field in package.json
echo "module.exports = { extends: ['@alexmarqs/commitlint-config'] };" > .commitlintrc.js
```

## Husky integration

To lint commits before they are created you can use install Husky and use the `commit-msg` hook:

```sh
# Install Husky
npm install husky -D
# or
yarn add husky -D

# Activate hooks (you can configure this in the 'prepare' life cycle script)
npx husky install
# or
yarn husky install

# Add hook
npx husky add .husky/commit-msg 'npx --no-install commitlint --edit "$1"'
# or
yarn husky add .husky/commit-msg 'yarn commitlint --edit $1'
```

For version 4 and under of Husky use the following instructions instead in your `package.json`:

```json
// package.json
{
  "husky": {
    "hooks": {
      "commit-msg": "commitlint -E HUSKY_GIT_PARAMS"
    }
  }
}
```

## License

MIT License © [alexmarqs](https://github.com/alexmarqs)
