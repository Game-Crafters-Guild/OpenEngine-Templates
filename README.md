# OpenEngine Templates

Home for OpenEngine **project templates** beyond the ones baked into the
editor.

## Where templates live today

The editor's built-in templates (Blank, Basic 3D, Open World) are **baked into
the editor build** — they ship as `<editor>/ProjectTemplates/` next to the
executable, sourced from `Apps/Editor/ProjectTemplates/` in the engine repo.
That's deliberate: creating a Blank project must always work, offline, with no
network dependency.

## What this repo is for

Downloadable template packs that don't need to ship with every install
(genre starters, larger demo content). These use the same manifest schema as
the [community catalog](https://github.com/Game-Crafters-Guild/OpenEngine-Community-Projects) —
a root `manifest.json` whose entries point at subfolders via
`source: { "type": "git", "url": ..., "path": ... }`. The editor fetches a
manifest and sparse-clones only the selected template's subtree.

The editor doesn't consume this repo yet; wiring a second (remote) template
source into the New Project → Templates tab is a planned follow-up. Until
then, contribute built-in template changes to the engine repo, and larger
sample projects to the community catalog.
