# shell-aliases

This role enables to install shell aliases globally on a system.

## Requirements

No requirements.

## Role Variables

| Name                      | Type      | Location            | Description                                                                                                                                    |
| ------------------------- | --------- | ------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| shell_aliases_shell_files | string[]  | `defaults/main.yml` | The location of shell files in which to write aliases. Defaults to `/etc/profile.d/custom-aliases.sh` and `/etc/profile.d/custom-aliases.csh`. |
| shell_aliases             | aliases[] | `defaults/main.yml` | The aliases to create on the target system. See below for defaults.                                                                            |
| shell_aliases_extras       | aliases[] | `defaults/main.yml` | An extra aliases object to keep the defaults and add your custom aliases. Defaults to `[]`.                                                    |

The `shell_aliases` and `shell_aliases_extras` are list of `aliases` objects, which are a dictionary composed of a `name` attribute for the alias name and the `command` attribute for the command to execute.

By default, the following aliases are defined in `shell_aliases`:

```yaml
- name: c
  command: "clear"
- name: untar
  command: "tar -xvf"
- name: untarz
  command: "tar -zxvf"
- name: ping
  command: "ping -c 5"
- name: ll
  command: "ls -al"
- name: hrep
  command: "history | grep"
```

## Dependencies

No dependencies.

## Example Playbook

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yaml
- hosts: servers
  roles:
    - { role: julb.shell_aliases }
```

## License

MIT

## Author Information

More to find on my [Github](https://github.com/julb).

## Contributing

This project is totally open source and contributors are welcome.

When you submit a PR, please ensure that the syntax has been checked.
