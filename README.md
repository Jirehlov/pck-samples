This repo contains almost all official builds of pcks of SiglusEngine I can find.

For files in folder 0, they are fully supported by `siglus-ssu` and can be compiled with `--serial` exactly.

For files in folder 1, they are fully supported by `siglus-ssu` and cannot be compiled with `--serial` exactly.

For files in folder 2, they are not really supported by `siglus-ssu` due to illegal grammars or other reasons, mostly because they are built for too early versions of SiglusEngine.

`profiles.json` records the configuration for every PCK, keyed by its path relative to this repository with `/` separators. Each entry has a `profile` number. An optional `allow_invalid: true` selects `--charset utf8 --allow-invalid` for embedded-source recompilation; the default is `false`. Decompile round trips always use strict UTF-8 and ignore this embedded-source option.

SiglusSceneScriptUtility CI downloads this list with the samples and runs exactly the recorded configuration. Missing or invalid entries fail the run without profile or charset fallback. Add or update the matching entry whenever a sample is added, renamed, or replaced. Folder `2` entries are used for decompile round trips only.
