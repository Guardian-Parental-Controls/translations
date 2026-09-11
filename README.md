# Guardian translations

This repository is the source of truth for all user-facing Guardian strings.
Catalogs are grouped by ISO 639-1 locale under `i18n/`.

## Contributor workflow

Open and merge a translation pull request before merging product code which
uses new or changed keys. Link the translation change from the product pull
request:

```text
Translations: #42
```

Product CI checks out that pull request and validates the product diff against
its catalogs. Product release builds only consume merged catalogs.

## Validate locally

```bash
python -m pip install PyYAML
python scripts/i18n/manage.py validate
```

To validate a sibling product checkout:

```bash
GUARDIAN_PRODUCT_ROOT=../platform \
  python scripts/i18n/manage.py check-usage
```
