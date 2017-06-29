# TeamSpeak Ansible Role

[Ansible](https://ansible.com) role for deploying [TeamSpeak](https://www.teamspeak.com) server using [Docker](https://www.docker.com) service. Uses [luzifer/teamspeak3](https://hub.docker.com/r/luzifer/teamspeak3) container image.

## Requirements

Ansible host:
  * [Ansible](https://ansible.com) 2.3.0.0 or newer
  * [Docker role](https://projects.task.gda.pl/ansible-roles/docker)
  * [Service role](https://projects.task.gda.pl/ansible-roles/service)

TeamSpeak host:
  * [Docker](https://www.docker.com)

## Role Variables

* *(optional)* `teamspeak_data_directory` - default `/opt/teamspeak`
* *(optional)* `teamspeak_container_image` - default `luzifer/teamspeak3:3.0.13.6`
* *(optional)* `teamspeak_service_name` - default `teamspeak`
* *(optional)* `teamspeak_server_port` - deafult `9987`
* *(optional)* `teamspeak_server_query_port` - default `10011`
* *(optional)* `teamspeak_server_file_transfer_port` - default `30033`

## Role Actions

* `deploy` - deploys TeamSpeak service

## Example Playbook

### Deploying TeamSpeak server

```yaml
- name: "deploy TeamSpeak server"
  hosts: "teamspeak"
  roles:
    - role: "teamspeak"
      action: "deploy"
      service_name: "teamspeak"
      teamspeak_data_directory: "/media/volume"
```

## License
[MIT](license.md)
