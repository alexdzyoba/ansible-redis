alexdzyoba.redis
================

Simple role to provision Redis for Debian as in [official Redis
Dockerfile](https://github.com/docker-library/redis/blob/99a06c057297421f9ea46934c342a2fc00644c4f/3.2/Dockerfile).

It's a showcase for [my post on Packer](https://alex.dzyoba.com/blog/packer-for-docker/)

Role Variables
--------------

Only user and group name can be safely set

    redis_user: redis
    redis_group: redis

If you change Redis version, please change SHA checksum because it's checked:

    redis_version: 3.2.11
    redis_download_sha: 31ae927cab09f90c9ca5954aab7aeecc3bb4da6087d3d12ba0a929ceb54081b5

By default sources will be put in /usr/src/redis

    redis_sources_dir: /usr/src/redis

Dependencies
------------

None

Example Playbook
----------------

```yaml
---

- hosts: all
  tasks:
  - import_role:
      name: alexdzyoba.redis
      vars:
        redis_version: 4.0.5
        redis_download_sha: d52bf355b96e20905916482962235e0442634c849934adb034f85362b31ed979
```

License
-------

MIT
