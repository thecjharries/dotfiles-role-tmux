# `dotfiles-role-tmux`

[![Build Status](https://travis-ci.org/thecjharries/dotfiles-role-tmux.svg?branch=master)](https://travis-ci.org/thecjharries/dotfiles-role-tmux)
[![GitHub tag](https://img.shields.io/github/tag/thecjharries/dotfiles-role-tmux.svg)](https://github.com/thecjharries/dotfiles-role-tmux)

## Requirements

Fedora 27 is recommended.

## Role Variables

Defaults are below.

```yml
---
owning_user: "{{ ansible_user }}"
owning_group: "{{ ansible_user }}"
root_dir: "/home/{{ ansible_user }}"
config_dir: "{{ root_dir }}/.config"

tmux_src_path: /opt/tmux
```

Additionally, these `vars` are set:

```yml
---
needed_packages:
  - gcc
  - make
  - autoconf
  - automake
  - pkg-config
  - libevent
  - libevent-devel
  - ncurses
  - ncurses-devel
```

## Dependencies

```yml
---
- src: git+https://github.com/thecjharries/dotfiles-role-common-software.git
- src: git+https://github.com/thecjharries/dotfiles-role-package-installer.git
- src: git+https://github.com/thecjharries/dotfiles-role-generic-template.git
- src: git+https://github.com/thecjharries/dotfiles-role-git.git
- src: git+https://github.com/thecjharries/dotfiles-role-repo-installer.git
```

## Example Playbook

```yml
---
- hosts: all

  roles:
    - role: dotfiles-role-tmux
```

## License

ISC
