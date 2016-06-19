# Ansible role: Sketch

[![Build Status](https://travis-ci.org/danbohea/ansible-role-sketch.svg?branch=master)](https://travis-ci.org/danbohea/ansible-role-sketch)

Installs Sketch, supporting tools & plugins on Mac OS X.


## Requirements

- Mac OS 10.10+


## Role Variables

All role default variables are listed below along with their respective default values.

```
sketch_apps:
  - sketch
  - sketch-tool
  - sketch-toolbox
```

Which Homebrew Cask apps to install.

```
sketch_plugins_dir: "/Users/{{ ansible_env.USER }}/Library/Application Support/com.bohemiancoding.sketch3/Plugins"
```

Where Sketch plugins should be installed. The default value is the default location for the current available version of Sketch.

```
sketch_plugin_repos:
  - { repo: "https://github.com/ddwht/sketch-dynamic-button.git", dest: "sketch-dynamic-button" }
  - { repo: "https://github.com/getflourish/Sketch-Style-Inventory.git", dest: "Sketch-Style-Inventory" }
  - { repo: "https://github.com/tylergaw/day-player.git", dest: "day-player" }
  - { repo: "https://github.com/timuric/Content-generator-sketch-plugin.git", dest: "Content-generator-sketch-plugin" }
  - { repo: "https://github.com/bomberstudios/sketch-commands.git", dest: "sketch-commands" }
  - { repo: "https://github.com/ScottSavarie/Clipboard-Fill.git", dest: "Clipboard-Fill" }
```

Sketch plugins to install.

- `repo` should contain the absolute URL to the plugin's public Git repository.
- `dest` will be used to name the subdirectory that the plugin will be cloned into.


## Dependencies

- [danbohea.homebrew](https://galaxy.ansible.com/danbohea/homebrew)


## Example Playbook

```
- hosts: macbook
  connection: local

  roles:
    - role: ansible-role-sketch
```

## License

MIT


## Author Information

This role was created by [Dan Bohea](http://bohea.co.uk) primarily for use with [Macsible](https://github.com/danbohea/macsible).
