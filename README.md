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
yarn add lint-staged husky prettier
npx mrm lint-staged
```

Then clean up package.json:

```json
{
  ...
  "lint-staged": {
    "*.{js,css,scss,json,md,ts,tsx}": "prettier --write",
  },
}
```

## Starting by testing out this repo

Using [`yarn`](https://github.com/hchiam/learning-yarn): (triple-click to select all)

```bash
git clone https://github.com/hchiam/learning-lint-staged.git && cd learning-lint-staged && yarn; # and then make changes and try to commit
```
