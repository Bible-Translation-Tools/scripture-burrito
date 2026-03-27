# Scripture Burrito for Wycliffe Associates

This fork documents the Wycliffe Associates usage profile for Scripture Burrito and keeps the validation rules in sync with that profile.

The goal is not to redefine Scripture Burrito. Instead, this repo narrows a few choices so that WACS tools and repositories express metadata consistently.

## WACS Usage Standard

- `idAuthorities` contains exactly one authority per burrito.
- When a burrito is online-capable, that authority is Wycliffe Associates Content Services at `https://content.bibletranslationtools.org`.
- When a burrito is created offline, the authority is the app that created it, such as `Orature` or `BTT-Writer`.
- `identification.name` comes from the Resource Container manifest `title`.
- `identification.abbreviation` comes from the Resource Container manifest `identifier`.
- `identification.primary` is keyed first by the ID authority and then by the repository path, such as `WA-Catalog/en_ulb`.
- `identification.primary` revisions are always `latest`.
- `meta.defaultLocale` is `en`.
- Exactly one language entry is allowed.
- Each language entry must include `tag`, `name`, and `scriptDirection`.
- Language `name` must include an `en` localized value.
- `confidential` is `false` unless a burrito is manually marked otherwise.
- `meta.generator` must include both `softwareName` and `softwareVersion`.
- Scripture text flavor metadata is fixed to `projectType: standard`, `translationType: newTranslation`, and `audience: common`.

## Resource Container Mapping

Resource Container is documented at [resource-container.readthedocs.io](https://resource-container.readthedocs.io/en/latest/).

For a Resource Container bundle, the mapping to Scripture Burrito is usually:

| Resource Container | Scripture Burrito |
| --- | --- |
| `manifest.yaml` | `metadata.json` |
| `dublin_core.title` | `identification.name` |
| `dublin_core.identifier` | `identification.abbreviation` |
| `dublin_core.language.identifier` | `languages[0].tag` |
| `dublin_core.language.title` | `languages[0].name.en` |
| `dublin_core.language.direction` | `languages[0].scriptDirection` |
| `dublin_core.format` | flavor-specific metadata and ingredient MIME types |
| `projects` / files in the container | `ingredients` and flavor-specific scope data |


## Building

Install the Sphinx tooling:

```bash
sudo apt-get install python-sphinx
pip install sphinx-jsonschema
```

Then build the docs from the `docs/` directory:

```bash
make
```

## Validation

Run the Python validator against the example metadata:

```bash
python3 code/validate.py docs/examples/artifacts/*.json
```

The JavaScript validator uses `ajv`:

```bash
npm install
node code/validate.js metadata docs/examples/artifacts/*.json
```

## Documentation Format

The docs are written in [reStructuredText](https://docutils.sourceforge.io/docs/ref/rst/restructuredtext.html), processed by [Sphinx](https://www.sphinx-doc.org/), and generated with `sphinx-jsonschema` where possible.
