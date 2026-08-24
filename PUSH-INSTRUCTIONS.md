# Publishing this kit

The repo exists and `origin` is already set:

```
https://github.com/collective-edge/collective-edge-brand-kit
```

It is public because jsDelivr serves public repos only. Do not make it private.

The CDN serves the `main` branch. Work lands on a branch, so nothing is live until that branch merges to `main`.

## 1. Verify

Both scripts pass before anything is pushed.

```bash
cd ~/collective-edge/collective-edge-brand-kit
python3 scripts/check-sync.py
python3 scripts/validate.py $(find snippets templates Examples -name '*.html' ! -name '*.before.html')
```

`check-sync.py` exits non-zero when a shared file drifts from the sibling kits, when `snippets/palette.css` is missing a semantic-contract variable, or when `snippets/type-tokens.json` and `snippets/type-system.css` disagree on a scale value.

`validate.py` exits non-zero on rules 1, 2, 5, 9, 10, 13 and 14 of `reference/type-system.md`. It reads its allowed values from `snippets/type-tokens.json`, so nothing about the ladder is hardcoded in it.

Seven files are shared byte for byte with `apex-brand-kit` and `royal-brand-kit`:

```
reference/type-system.md
NEW-BRAND.md
brands.json
snippets/type-system.css
snippets/type-tokens.json
scripts/validate.py
scripts/check-sync.py
```

Never edit one of them for a single brand. Change it here, copy it into the other two kits, then run `check-sync.py` inside all three before any of them is pushed.

## 2. Push the branch

```bash
git add .
git commit -m "Describe what changed"
git push -u origin HEAD
```

## 3. Merge to publish

```bash
git checkout main
git merge --no-ff type-system-v1
git push
```

## 4. Confirm the CDN

Give jsDelivr a minute, then load:

```
https://cdn.jsdelivr.net/gh/collective-edge/collective-edge-brand-kit@main/snippets/type-system.css
```

Every other file serves from the same base URL with its repo path appended. jsDelivr caches an `@main` path for up to twelve hours. To force a refresh, load the same path once under `https://purge.jsdelivr.net/gh/...`.

## 5. Tag a version

Production materials pin to a tag rather than to `@main`:

```bash
git tag v1.0
git push --tags
```

In a pinned URL, replace `@main` with `@v1.0`. Bump the minor version for an additive change. Bump the major version when a value in section 3, 4 or 5 of `reference/type-system.md` changes, or when the palette or the marks change.

## 6. Teammates

Install once:

```bash
git clone https://github.com/collective-edge/collective-edge-brand-kit ~/.claude/skills/collective-edge-brand-guidelines
```

Update:

```bash
git -C ~/.claude/skills/collective-edge-brand-guidelines pull
```
