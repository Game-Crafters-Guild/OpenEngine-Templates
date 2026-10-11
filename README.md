# OpenEngine Templates

The OpenEngine editor's built-in project templates, published as a catalog.

## What is here

| Template | Contents |
| --- | --- |
| [Blank](templates/blank) | An empty scene: a camera, a sun with shadows, a sky and a post-process volume. |
| [Basic 3D](templates/basic3d) | The same scene with a ground plane, four cubes and an editable `Default` material. |

These mirror the templates built into the editor (`Apps/Editor/ProjectTemplates/` in the
engine repository), which ship next to the editor so creating a project always works
offline. This repository tracks them; when the two differ, the editor's copy is the
reference.

Each template is a project root: an `Assets/` folder whose only scene is
`Assets/Scenes/Main.scene`, which a new project opens on. Neither template names a render
pipeline, so both draw with the engine's ForwardPlus pipeline.

## Layout

- `manifest.json` lists the templates in the same schema as the
  [community catalog](https://github.com/Game-Crafters-Guild/OpenEngine-Community-Projects):
  each entry's `source` is `{ "type": "git", "url": ..., "path": "templates/<id>" }`, and
  the editor sparse-clones only that folder.
- `templates/<id>/` holds the project and its `thumbnail.png`.

## Using this catalog in the editor

The editor reads one remote catalog, shown on the **New project → Community** tab. To list
these templates there instead of the community projects, set `communityManifestSource` in
the editor's `Preferences.json` to:

```
https://raw.githubusercontent.com/Game-Crafters-Guild/OpenEngine-Templates/main/manifest.json
```

Remove the key to return to the community catalog. The editor does not yet read a second
remote catalog alongside the first.

## License

MIT, see [LICENSE](LICENSE).
