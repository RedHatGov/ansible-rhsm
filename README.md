rhsm
=========

This role allows attaching a RHEL system to a Red Hat Subscription

Requirements
------------

You must have a valid Red Hat subscription for the product you are trying to
subscribe. You should also know the pool id(s) for that subscription.

Role Variables
--------------

| Variable        | Required | Default  | Description                                                                                                                                                                                                                                     |
| --------------- | -------- | -------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `rhsm_username` | :heavy_check_mark:      |  | The Red Hat Network (RHN) username that owns the subscriptions |
| `rhsm_password` | :heavy_check_mark:      |  | The Red Hat Network (RHN) password for the user that owns the subscriptions |
| `rhsm_pool` | :heavy_check_mark:      |  | This is the subscription pool id(s) for the Red Hat Product you are subscribing to. Can be a single pool id or a list |
| `rhsm_consumer_name` | :x:      | `host.example.com` | A name to send along during registration to easily identify the subscribed system |

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: localhost
  remote_user: root
  vars:
    rhsm_username: rhnuser
    rhsm_password: p@ssw0rd
    rhsm_pool: "8...z"
    rhsm_consumer_name: "host.example.com"
    rhsm_repos:
      - rhel-7-server-rpms
      - rhel-7-server-extras-rpms
  roles:
    - redhatgov.rhsm
```

License
-------

GPLv3

Author Information
------------------

[Red Hat North American Public Sector Solution Architects](https://redhatgov.io)
