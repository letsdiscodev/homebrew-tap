# Disco Homebrew Tap

this is the internal homebrew tap allowing macOS users to install the Disco CLI

docs (on how to use the CLI, Disco, etc.) are available at https://docs.letsdisco.dev/

TLDR to install disco-cli, run `brew install letsdiscodev/tap/disco-cli`

to upgrade to the latest version:

```bash
brew update
brew upgrade disco-cli
```

#### internals

right now, to create a new homebrew release:
- make a new release in [the cli repo](https://github.com/letsdiscodev/disco-cli)
- download the .tar.gz release
- runs `sha256sum` on the release file
- update the [disco-cli.rb](https://github.com/letsdiscodev/homebrew-tap/blob/main/Formula/disco-cli.rb) file in this repo by pointing the `url` to the latest .tar.gz, and setting the `sha256` to the latest file hash
- git add, push
- then, `brew update` + `brew upgrade disco-cli` should install/update the latest version
