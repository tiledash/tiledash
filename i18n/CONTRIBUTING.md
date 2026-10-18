# Helping with translations

Thank you for helping Tiledash speak your language. Translations live here, in `i18n/`.

## What you can edit

| File                               | What it is                                                           |
| ---------------------------------- | -------------------------------------------------------------------- |
| `locales/<language>/<bundle>.json` | The translations: one file per language (nl, de, es, fr) and bundle. |
| `glossary.yaml`                    | The agreed words for terms like "wall panel" or "tile".              |
| `style/<language>.md`              | How the app talks in that language (tone, quotes, spacing).          |

Please change nothing else. `source/` (the English) and `tools/` (the checker) are generated in our source repository and are overwritten by it, and `languages.yaml` (which languages are out of Beta) is ours to decide. A pull request that changes them fails its check.

## Reading the English

`source/<bundle>.json` holds every English message with what you need to translate it well:

- `en`: the English text.
- `context`: where the text shows up and what it means. Read it first.
- `params`: what each `{value}` in the text stands for.
- `maxLength`: the longest the translation may be, because the text has to fit its place on screen.

The same message id is the key in `locales/<language>/<bundle>.json`.

## Writing a translation

An entry looks like this:

```json
"account.locale.title": {
  "text": "Taal en regio",
  "source": "003e875495",
  "by": "human",
  "reviewed": true
}
```

- Keep the `{values}`, the `<link>…</link>` tags and the plural and select structure of the English. Translate only the words. The checker tells you when something is missing or has changed.
- Follow the glossary and the style guide of your language. How to address people (formal or informal) is already decided there.
- **`source` is a fingerprint of the English the translation was made from**: the first 10 characters of its SHA-256. When you fix an entry, leave `source` as it is. When you add one, or when the English has changed, set it to the fingerprint of the current English:

  ```sh
  node -e "console.log(require('crypto').createHash('sha256').update(process.argv[1]).digest('hex').slice(0, 10))" "The English text"
  ```

  A translation whose `source` doesn't match the current English was made for older text and is not imported.

- You don't need to touch `by` and `reviewed`: when we import your change they become `human` and `reviewed`.

## Checking your work

You need only Node (version 20 or newer), no install:

```sh
node i18n/tools/check.mjs
```

It reports missing and outdated translations as warnings, and anything wrong (a lost `{value}`, a missing plural form, a text that is too long, a glossary word that isn't followed) as an error. The same check runs on your pull request.

## What happens to your pull request

Pull requests here are not merged. We import them into our source repository, which is where `i18n/` is maintained, and then close the pull request with a comment. Your translations come back here with our next sync, and you are credited as co-author of the commit that imports them.

If something can't be imported (usually: it was translated against English that has changed since), we say what and why in the pull request.
