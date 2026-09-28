# Cross-space linking test

A GitBook site synced with Git Sync at the site level. Each folder is a space of its own section, and the pages link to the other spaces with relative Markdown links.

| Folder | Section | Pages |
| --- | --- | --- |
| [guides](guides/) | Guides (default) | README, quickstart, setup/README, setup/environment |
| [api](api/) | API | README, authentication, endpoints/README, endpoints/users |
| [sdks](sdks/) | SDKs | README, javascript, python |
| [faq](faq/) | FAQ | README, troubleshooting |
| [changelog](changelog/) | Changelog | README, 2026 |

This file is outside every space, so link repairs never change it: [Quickstart](guides/quickstart.md).

## Link kinds covered

* Inline links, with and without anchors (`#api-tokens`, `#install`, `#variables`, `#oauth`, `#configure`)
* Reference-style definitions (`guides/quickstart.md`)
* `{% content-ref %}` blocks, including a folder target (`sdks/python.md`)
* HTML `<a href>` (`guides/quickstart.md`)
* Folder links to a `README.md` (`../../api/endpoints/`, `../api/`, `../../sdks/`)
* Links two folders up (`guides/setup/environment.md`, `api/endpoints/users.md`)
* Links in inline code and code blocks, which must stay untouched (`faq/troubleshooting.md`)

## Test plan

1. **Import.** Connect the site to this repository. Links between spaces show as links to the target pages.
2. **Flag off.** Edit a paragraph in `guides/quickstart.md` in GitBook. Its links to other spaces export as `app.gitbook.com` URLs.
3. **Flag on, edit.** Enable `CROSS_SPACE_LINKING`, then edit the page again. Its links to other spaces export as relative links. Other pages keep their current links.
4. **Flag on, force export.** Every page exports its links to other spaces as relative links.
5. **Move a linked page.** Change the slug of **API > Authentication** to `auth`. The export commit renames `api/authentication.md` to `api/auth.md` and rewrites the links to it in `guides`, `sdks` and `faq`, in the same commit. This file, the inline code and the code block stay unchanged. Each repaired space then imports that commit.
6. **Move a folder page.** Move **Guides > Setup** under Quickstart, or change its slug. The links from `api`, `sdks` and `faq` to `guides/setup/...` follow it.
7. **Race.** Right after step 5, edit `faq/troubleshooting.md` in GitBook before the FAQ space imports the repair. Check that the `#oauth` link keeps pointing to `api/auth.md`.
