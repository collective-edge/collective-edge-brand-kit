# How to push this to GitHub (one-time, ~3 minutes)

Everything is already prepared in this folder. You just need to push it. The CDN (jsDelivr) only works against a **public** GitHub repo, so the repo must be public.

## Step 1. Create the empty repo on GitHub

Go to **https://github.com/organizations/collective-edge/repositories/new** and create:

- **Repository name:** `collective-edge-brand-kit`
- **Visibility:** **Public** (required for the jsDelivr CDN to work)
- **Do NOT** initialize with a README, .gitignore, or license — this folder already has those.

Click **Create repository**.

## Step 2. Push from terminal

```bash
cd ~/collective-edge/collective-edge-brand-kit
git init
git add .
git commit -m "Initial Collective Edge brand kit"
git branch -M main
git remote add origin https://github.com/collective-edge/collective-edge-brand-kit.git
git push -u origin main
```

If prompted to authenticate, the easiest path is the [GitHub CLI](https://cli.github.com/): `gh auth login` once, then re-run the push.

## Step 3. Verify the CDN is live

After pushing, hit this URL in a browser (give jsDelivr 30–60 seconds the first time):

```
https://cdn.jsdelivr.net/gh/collective-edge/collective-edge-brand-kit@main/assets/logos/horizontal-white.svg
```

You should see the white Collective Edge lockup. The font, colors.json, and snippets are all at the same base URL.

## Step 4. Tell teammates

Share this single line. They run it once and Claude on their machine applies the brand automatically:

```bash
git clone https://github.com/collective-edge/collective-edge-brand-kit ~/.claude/skills/collective-edge-brand-guidelines
```

## Updating later

Edit any file in this folder, then:

```bash
cd ~/collective-edge/collective-edge-brand-kit
git add . && git commit -m "Describe what changed" && git push
```

Changes go live on the CDN within a minute or two. Anyone with the skill installed pulls updates with `git pull`.

## Versioning (optional, for production safety)

Once stable, tag a release so production materials can pin to a fixed version:

```bash
git tag v1.0
git push --tags
```

Then in CDN URLs, replace `@main` with `@v1.0`. Bump the tag on breaking changes (logo redesign, palette shift).
