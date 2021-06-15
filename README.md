# Learning `lint-staged`

Just one of the things I'm learning. <https://github.com/hchiam/learning>

Automatically include code style fixes in your commits with `lint-staged`, set up with `husky`.

<https://www.npmjs.com/package/lint-staged>

<https://github.com/okonet/lint-staged>

<https://medium.com/@okonetchnikov/make-linting-great-again-f3890e1ad6b8#.8qepn2b5l>

## From scratch

Using [`yarn`](https://github.com/hchiam/learning-yarn):

```bash
yarn init
yarn --dev add lint-staged husky@^4.3.0 prettier jest
npx mrm lint-staged
```

Then clean up your package.json to look something like this:

```json
{
  ...
  "scripts": {
    "test": "jest --bail --findRelatedTests",
    "lint": "prettier --write *.{js,css,html,scss,json,md,ts,tsx}"
  },
  "dependencies": {},
  "devDependencies": {
    "husky": "^4.3.0",
    "jest": "^27.0.4",
    "lint-staged": "^11.0.0",
    "prettier": "^2.3.1"
  },
  "husky": {
    "hooks": {
      "pre-commit": "lint-staged"
    }
  },
  "lint-staged": {
    "**/*.js": [
      "jest --bail --findRelatedTests"
    ],
    "*.{js,css,html,scss,json,md,ts,tsx}": "prettier --write"
  }
}
```

**_Note:_** it's important that you include `"prepare": "husky install"` in the package.json file, otherwise when you `git clone` and `yarn`, `lint-staged` might not run.

## Starting by testing out this repo

Using [`yarn`](https://github.com/hchiam/learning-yarn): (triple-click to select all)

```bash
git clone https://github.com/hchiam/learning-lint-staged.git && cd learning-lint-staged && yarn; # and then make changes and try to commit
```
