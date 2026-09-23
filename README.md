# hindsight-data-template

Public default data folder for hindsight-compose.

Default `data/` folder for
[hindsight-compose](https://github.com/intisy-compose/hindsight-compose), so a fresh
`git clone --recursive` runs out of the box.

It is mounted at `data/`: the db-backup sidecar writes its SQL dumps to `hindsight/`
and the llama container reads its model from `llama/`. Both are runtime state and gitignored, so
this template tracks no files of its own; the folders are created on first start.

## Use your own data

Fork or replace this repo, then point the folder at it from the hindsight-compose checkout:

```powershell
.\docker-compose.ps1 data use <owner/repo[@ref]>   # your own data repo, optionally a branch
.\docker-compose.ps1 data use                      # back to this template
```

Commit configuration, not runtime state.

## License

[![MIT License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
