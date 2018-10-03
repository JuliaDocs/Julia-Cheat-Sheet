# Translation Guide

TL;DR:

- See `_config.yml`, `index.br.html`, `_includes/` and `assets/`

The translation of this cheat-sheet requires the followings steps:

- Choose a tag for your language, such as `en` for English or `br` for Brazilian
  Portuguese;
- On [`_config.yml`](_config.yml), add your tag and translate the given phrases;
- Copy `index.html` to `index.TAG.html`, where TAG is your tag;
- Modify `index.TAG.html`, changing `lang: TAG` and `permalink: /TAG/`;
- Copy the folder `_includes/en/` to `_includes/TAG/`, i.e., create a folder `TAG`
  inside `_includes` with a copy of all the `.md` files; **don't change the .md names**;
- Download an icon for your language in **svg**, preferably from
  [https://www.flaticon.com/packs/countrys-flags](Country Flags by Freepik), since
  it is already attributed on the footer; save it to `assets/TAG.svg`;
- On file `_data/blocks.yml`, add a `  TAG: translated title` line for each title;
- Translate each block in `_includes/TAG`.

