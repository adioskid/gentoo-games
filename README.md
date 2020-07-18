## Gentoo overlay to support docker image for games.

overlay with some updates.

## with local overlays

[Local overlays](https://wiki.gentoo.org/wiki/Custom_repository) should be managed via `/etc/portage/repos.conf/`.
create a `/etc/portage/repos.conf/gentoo-games.conf` file containing precisely:

```
[gentoo-games]
location = /var/db/repos/gentoo-games
masters = gentoo
sync-type = git
sync-uri = https://github.com/adioskid/gentoo-games.git
auto-sync = Yes
priority= 99
```

Afterwards, simply run `emerge --sync`, and Portage should seamlessly make all our ebuilds available.

## with layman

Invoke the following:

You can also use the Layman tool to add and sync the repository, read the instructions on the [Gentoo Wiki](https://wiki.gentoo.org/wiki/Layman#Adding_custom_repositories).

```
# layman -o https://raw.github.com/adioskid/gentoo-games/master/repositories.xml -f -a gentoo-games
```