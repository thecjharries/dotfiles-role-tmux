# `dotfiles-tmux-role`

[![Build Status](https://travis-ci.org/thecjharries/dotfiles-tmux-role.svg?branch=master)](https://travis-ci.org/thecjharries/dotfiles-tmux-role)

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
- src: git+https://github.com/thecjharries/dotfiles-common-software-role.git
- src: git+https://github.com/thecjharries/dotfiles-package-installer-role.git
- src: git+https://github.com/thecjharries/dotfiles-generic-template-role.git
- src: git+https://github.com/thecjharries/dotfiles-git-role.git
- src: git+https://github.com/thecjharries/dotfiles-repo-installer-role.git
```

## Example Playbook

```yml
---
- hosts: all

  roles:
    - role: dotfiles-tmux-role
```

## License

ISC
