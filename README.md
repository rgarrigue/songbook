# Songbook

This is all about generating quickly an ebook with a bunch of songs' lyrics, so I can put it on my eReader. It's done using [mdBook](https://rust-lang.github.io/mdBook), plus GitHub Actions to automate it on each tag.

Regarding the lyrics themselves, all rights belong to their respective owners.

## Install

Install Rust which includes Cargo, then mdbook itself

```bash
curl https://sh.rustup.rs -sSf | sh
cargo install mdbook mdbook-epub
```

## Add your content

If this is the first time, adapt `./book.toml` (authors, title, language) and `./.github/workflows/main.yml` (asset_path and asset_name).

Write your chapters in `./src/` folder, as `.md` files.

Then update the `SUMMARY.md`. Running `./generate_summary.sh` is enough for my own usage, it generates one based on alphabetical order, naming chapters by files names.

## Generate the ebook

Run `mdbook build`. The result will be in `./book/` folder, you can copy the `./book/epub/Songbook.epub` on your eReader straight away.

To automate this I added a Github Actions, so it'll be done on each git tag, the `.pub` file being published in Github release and the `html` directory as Github Pages.