# Cross-space linking test

A GitBook site synced with Git Sync at the site level: 200 spaces in 18 sections, with about 5,500 relative Markdown links, of which about 4,100 link to another space.

## Structure

The 5 hand-written spaces each have their own section:

| Folder | Section | Pages |
| --- | --- | --- |
| [guides](guides/) | Guides (default) | README, quickstart, setup/README, setup/environment |
| [api](api/) | API | README, authentication, endpoints/README, endpoints/users |
| [sdks](sdks/) | SDKs | README, javascript, python |
| [faq](faq/) | FAQ | README, troubleshooting |
| [changelog](changelog/) | Changelog | README, 2026 |

The 195 generated spaces live in [products](products/), 15 per section (**Products 01** to **Products 13**). Each one has README, guide, setup/README, setup/advanced and faq pages. They link to the hand-written spaces, to 8 random other products, and to the previous and next product in a chain.

Pages with the most incoming links, for stress tests:

| Page | Linked from |
| --- | --- |
| `api/authentication.md` | 397 files in 199 spaces |
| `guides/quickstart.md` | 201 files in 200 spaces |
| `guides/setup/environment.md` | 200 files in 199 spaces |
| `api/endpoints/users.md` | 198 files in 198 spaces |
| `guides/setup/README.md` (folder links) | 196 files in 196 spaces |

This file is outside every space, so link repairs never change it: [Quickstart](guides/quickstart.md).

## Link kinds covered

* Inline links, with and without anchors (`#api-tokens`, `#install`, `#variables`, `#oauth`, `#configure`, `#details`, `#options`, `#overview`, `#invalid-token`)
* Reference-style definitions (`guides/quickstart.md`, every product `guide.md`)
* `{% content-ref %}` blocks, including a folder target (`sdks/python.md`, every product README)
* HTML `<a href>` (`guides/quickstart.md`, every product `guide.md`)
* Folder links to a `README.md` (`../../api/endpoints/`, `../product-042/`, `../../guides/setup/`)
* Links two and three folders up (`guides/setup/environment.md`, every product `setup/` page)
* Links in inline code and code blocks, which must stay untouched (`faq/troubleshooting.md`, every product `faq.md`)

## Test plan

1. **Import.** Connect the site to this repository. All 200 spaces are created and imported. Links between spaces show as links to the target pages.
2. **Flag off.** Edit a paragraph in `guides/quickstart.md` in GitBook. Its links to other spaces export as `app.gitbook.com` URLs.
3. **Flag on, edit.** Enable `CROSS_SPACE_LINKING`, then edit the page again. Its links to other spaces export as relative links. Other pages keep their current links.
4. **Flag on, force export.** Every page exports its links to other spaces as relative links.
5. **Move a linked page.** Change the slug of **API > Authentication** to `auth`. A single export commit renames `api/authentication.md` to `api/auth.md` and rewrites the links to it in the other 198 spaces (397 files). This file, the inline code and the code blocks stay unchanged. The other spaces import nothing, and their links in GitBook still point to the page.
6. **Move a folder page.** Move **Guides > Setup** under Quickstart, or change its slug. The folder links to `guides/setup/` from 195 products follow it, as do the links to `guides/setup/environment.md`.
7. **Race.** Right after step 5, edit a few product pages that link to Authentication, for example `products/product-001/guide.md` (the `#oauth` link). Their exports keep `../../api/auth.md#oauth`, and the pages nobody edited keep their repaired links too.
8. **Chain.** Change the slug of a product's `setup/advanced.md`, for example in **Product 050**. Only the previous product's `setup/advanced.md` and the few random products linking to it are rewritten.
9. **Repeat moves.** Move `api/auth.md` back to `authentication`, then again, and check each commit rewrites the same files and nothing else.
