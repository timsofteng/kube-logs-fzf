### Descriptions

Conveniently view logs using fzf.

## Features

- Interactive viewing of logs.

- Integration with `fzf` for fuzzy search by pod name.

- Pre-filter the list of pods.

- Integration with `lnav` for advanced log viewing.

- Ability to view logs for several pods in real time.

- Configurable:
    - Filter/prefix/sort of file system entries.
    - Mappings used for common explorer actions.
    - UI options: whether to show preview of file/directory under cursor, etc.

See `*MiniFiles-examples*` tag in help file for some common configuration examples.

Notes:

- This script is written and thoroughly tested on UNIX. Support for other platform/OS (like Windows) is no guarantee.


## Dependencies
Required applications:
  - fzf
  - kubectl
  - coreutils (e.g grep, sed, etc)

Optional applications:
  - lnav (for advanced mode)

## Installation

Create a file with a convenient name for you (I recommend `kube-logs-fzf`) and place it in one of the `$PATH` directories (I recommend adding to `PATH` a directory from the user's home directory, for example `$HOME/.local /bin`).

Run the command 
```
chmod +x ./kube-logs-fzf
```

This is all. You can now use the `kube-logs-fzf` command like any other program from your terminal.

## Config

Use environment variables as a way to configurate script.

Options list:
  - `KUBE_LOGS_FZF_NAMESPACE` to configure kubectl --namespace


## Quick start

```bash
kube-logs-fzf
```

Filter pods by part of the name, "," is a separator
```bash
kube-logs-fzf -p my_pod_one,my_pod_t 
```

Filter pods by part of the name and skip picking stage
NOTE! This will not work if there is more than one pod in the list
```bash
kube-logs-fzf -p my_pod_one,my_pod_t -S 
```

Use advanced mode
```bash
kube-logs-fzf -p my_pod_one,my_pod_t -SA
```

To get more help.
```bash
kube-logs-fzf -h
```
