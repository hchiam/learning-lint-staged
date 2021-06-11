# Learning `lint-staged`

Just one of the things I'm learning. <https://github.com/hchiam/learning>

Automatically include code style fixes in your commits with `lint-staged`, set up with `husky`.

<https://www.npmjs.com/package/lint-staged>

<https://github.com/okonet/lint-staged>

<https://medium.com/@okonetchnikov/make-linting-great-again-f3890e1ad6b8#.8qepn2b5l>

## From scratch

Using `npm` (setup after cloning this repo didn't seem to work with [`yarn`](https://github.com/hchiam/learning-yarn)):

```bash
npm init
npm -D install lint-staged husky prettier jest
npx mrm lint-staged
```

Then clean up your package.json to look something like this:

```json
{
  ...
  "scripts": {
    "test": "jest --bail --findRelatedTests",
    "lint": "prettier --write *.{js,css,scss,json,md,ts,tsx}",
    "prepare": "husky install"
  },
  "dependencies": {},
  "devDependencies": {
    "husky": "^6.0.0",
    "jest": "^27.0.4",
    "lint-staged": "^11.0.0",
    "prettier": "^2.3.1"
  },
  "lint-staged": {
    "**/*.js": [
      "jest --bail --findRelatedTests"
    ],
    "*.{js,css,scss,json,md,ts,tsx}": "prettier --write"
  }
}
```

## Starting by testing out this repo

Using `npm` (setup after cloning this repo didn't seem to work with [`yarn`](https://github.com/hchiam/learning-yarn)):

```bash
git clone https://github.com/hchiam/learning-lint-staged.git && cd learning-lint-staged && npm install; # and then make changes and try to commit
```
