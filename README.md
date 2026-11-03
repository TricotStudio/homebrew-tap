# Homebrew tap for Tricot

Tricot is a shared planning board where humans and agents make decisions together. Its source is at https://github.com/TricotStudio/tricot.

Install it with Homebrew:

```sh
brew install tricotstudio/tap/tricot
```

Then run `tricot`. `brew upgrade tricot` moves to a new version once it is here.

## Updating the formula

`Formula/tricot.rb` is written in the tricot repository, not here. It installs the file attached to that version's GitHub release, the same file npm gets. Once the GitHub release for a version is out (npm needn't have it yet), from the tricot repository:

```sh
node scripts/homebrew-formula.mjs   # fetches the release's file, checks it against GitHub's digest and npm's record, writes its sha256
```

That writes `packaging/homebrew/Formula/tricot.rb`. Copy it to `Formula/tricot.rb` in this repository, commit it ("Update tricot to x.y.z") and push to `main`. The tricot repository's RELEASING.md has the whole release.
