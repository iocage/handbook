---
title: Provisioning
---
FreeNAS is also using iocage to provide their users a graphical user interface for FreeBSD jails.
ixSystems maintains several so called plugins (called ix-iocage-plugins in libioc).
The provisioning feature of libioc already has support for those plugins.

The list of available ix-iocage-plugins can be found on [GitHub](https://github.com/freenas/iocage-ix-plugins).
They can be either installed with the command line tool `{{site.ioc_cli_tool}}` or using the iocage Python module directly.

First the jail has to be configured with the according properties:

```sh
{{site.ioc_cli_tool}} create my-jenkins-jail \
  provisioning.method="ix" \
  provisioning.source="plexmediaserver"

{{site.ioc_cli_tool}} provision my-jenkins-jail
```

Idempotence of the provisioner allows to call the provision command multiple times to keep a jail or a template up to date.