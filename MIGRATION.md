# WordPress migration notes

Inventory performed from the public site on 16 November 2026. The visible homepage contained Joshua Oladipo’s name, a generic biography placeholder, a Projects link, and an apparent sample design post containing lorem ipsum. None of that unverified/sample copy has been imported as Joshua’s work.

## Imported asset

- `assets/images/oladipo-2.jpeg` is the retained original profile photograph downloaded from `/wp-content/uploads/2025/05/oladipo-2.jpeg`.
- Hugo generates responsive WebP derivatives at build time. The source is never hotlinked.

## Content gaps

- Replace the short configurable introduction in `hugo.yaml` after Joshua approves the wording.
- Replace the placeholder text in `content/about.md` with a verified biography and public contact links.
- Add only verified posts/projects. Preserve original dates and slugs in front matter when migrating real content.
- Confirm whether any additional public WordPress URLs exist before launch.

## Redirect map

No changed verified content URLs have been identified yet. When a real WordPress item moves, add its old path as a Hugo `aliases` entry in that content file; Hugo will generate a redirect page.

| Previous URL | New URL | Status |
| --- | --- | --- |
| `/wp-content/uploads/2025/05/oladipo-2.jpeg` | Build-generated profile image URL | Asset retained locally; no launch redirect proposed |

Do not remove or overwrite the WordPress site until this inventory has been reviewed and the new build has concrete launch approval.

