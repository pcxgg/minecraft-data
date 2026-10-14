# node loader (pcxgg packaging shim)

The files in this directory are copied from
[PrismarineJS/node-minecraft-data](https://github.com/PrismarineJS/node-minecraft-data)
3.117.0 (MIT, Romain Beaumont and PrismarineJS contributors). Upstream publishes
the `minecraft-data` npm package from that repo with this repo as a git submodule;
pcxgg has no fork of it, so the loader is vendored here to make this repo
directly installable:

    "minecraft-data": "github:pcxgg/minecraft-data#<commit sha>"

Only the require paths were changed (`./minecraft-data/data/...` -> `../data/...`).
`data.js` is generated and committed so no install-time build is needed; regenerate
it after changing `data/dataPaths.json`:

    node node/bin/generate_data.js
