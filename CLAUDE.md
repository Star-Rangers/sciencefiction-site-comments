# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with
this repository.

## What this is

A repository with no code. It exists to host the GitHub Discussions that
[giscus](https://giscus.app) maps reader comments to for the *Fian Ilchruinne* sites (the work formerly titled *Star Rangers*; the repository slug and this organisation's name keep the old title on purpose). It is the shared pool: since 2026-09-04 every domain's build posts its general-tier pages here, fianilchruinne.com (the GitHub Pages build itself since 2026-10-06), sciencefiction.site, starquest.site, young.fianilchruinne.com and the contemplative editions alike, so community discussion stays in one place. The two editions whose entry in star-rangers' `lib/editions.js` sets `commentsEnabled: false`, undercover-pets.com (the children's edition, ruled 2026-09-04) and told.fianilchruinne.com, show no comment box and post nowhere. This file was written on 2026-09-29 alongside the sister board's copy and landed here on 2026-10-26; the README says the same since that day.

Nothing here builds, tests or deploys. A pull request here changes `README.md`
or this file, and the Discussions are administered in the repository's
Discussions tab, not in git.

## What reads this repository, and what must not change

- **`dermot-r-cochran/star-rangers`** is the only consumer. Its
  `src/_data/giscus.js` registers this repository as the **`default`** profile
  with the repository id and four Discussion category ids hardcoded, and its
  `TECHNICAL-README.md` (*Discussion forum (giscus)*) is the authoritative
  description of the mapping. Four categories are mapped to page types and
  locked to Announcement format so only the giscus app can open threads in
  them: **Characters**, **Lore & Worldbuilding**, **Episodes Discussion** and
  **Journal**. Five more are open community categories: Announcements,
  General, Q&A, Theories & Predictions, Fan Creations.
- **Never rename, delete or recreate the four mapped categories, and never
  recreate this repository.** The ids are the identity giscus posts under; a
  new category or a new repository has new ids, and every existing thread is
  orphaned until `giscus.js` is repointed.
- **A thread's identity comes from star-rangers, not from here.** Characters,
  lore, glossary, codex and journal pages map by pathname; chapters and
  per-viewpoint scene pages map by a permanent `comment_id` in their front
  matter, which moves with the content when chapters are renumbered. Nothing
  in this repository decides which page a thread belongs to.
- **`scripts/fetch-giscus-ids.js` is an older copy of the star-rangers script
  of the same name and cannot run here**: it looks for `../src/_data/giscus.js`,
  which this repository does not have. The authoritative copy is
  `star-rangers/scripts/fetch-giscus-ids.js` (`npm run fetch-giscus-ids`
  there), which has since gained a `--repo` flag for targeting this
  repository from that checkout. Don't develop the copy here.

## Related repositories

The map of Dermot's public repositories and what crosses between them is
`RELATED-REPOSITORIES.md` in `dermot-r-cochran/star-rangers`; this section
names only this repository's own neighbours (added 2026-09-29 at his
direction).

- **`dermot-r-cochran/star-rangers`** — the site whose pages post here, as
  above. Comments are switched off per build there (`COMMENTS_ENABLED`), never
  here.
- **`Star-Rangers/churchspace-site-comments`** — the sister board, holding
  the threads of the church-space storyline thread on any domain that renders
  it; on GitHub it is a fork of this repository. Same shape, same rules, its
  own ids.
