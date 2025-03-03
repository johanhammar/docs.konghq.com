---
title: Kong Mesh with macOS
no_search: true
---

## macOS

To install and run {{site.mesh_product_name}} on macOS, execute the following
steps:

* [1. Download {{site.mesh_product_name}}](#1-download-kong-mesh)
* [2. Configure the license](#2-configure-the-license)
* [3. Follow Kuma instructions](#3-follow-kuma-instructions)

### 1. Download {{site.mesh_product_name}}

To run {{site.mesh_product_name}} on macOS, you can choose from the following
installation methods:

{% navtabs %}
{% navtab Script %}

Run the following script to automatically detect the operating system and
download {{site.mesh_product_name}}:

```sh
$ curl -L https://docs.konghq.com/mesh/installer.sh | sh -
```

{% endnavtab %}
{% navtab Manually %}

You can also [download](https://kong.bintray.com/kong-mesh/kong-mesh-{{page.kong_latest.version}}-darwin-amd64.tar.gz)
the distribution manually.

Then, extract the archive with:

```sh
$ tar xvzf kong-mesh-{{page.kong_latest.version}}*.tar.gz
```

{% endnavtab %}
{% endnavtabs %}

### 2. Configure The License

Before running the {{site.mesh_product_name}} control plane process - which is served by the `kuma-cp` executable - we need to make sure that we have a valid {{site.mesh_product_name}} license in place.

This can be done by running the control plane with:

```sh
$ KUMA_LICENSE_PATH=license.json kuma-cp run
```

Where `license.json` is the path to a valid {{site.mesh_product_name}} license file on the file system.

### 3. Follow Kuma Instructions

After downloading the {{site.mesh_product_name}} binaries, the remaining
installation instructions for Kuma are fully compatible with
{{site.mesh_product_name}}, except you will be running the
{{site.mesh_product_name}} binaries instead of the vanilla Kuma ones.

To continue the installation, start from the second installation step in
[the official Kuma installation guide](https://kuma.io/docs/0.7.1/installation/macos/#_2-run-kuma) keeping in mind that we need to run the control plane with the appropriate license file as described on this page.
