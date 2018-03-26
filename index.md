# geOrchestra packages


## Docker images

Images tagged `latest` (built from geOrchestra `master` branch) are available on [Docker hub](https://hub.docker.com/u/georchestra/). 


## Web archives (war)

The latest generic webapps, as compiled by our CIs, are available here:

- [master](https://packages.georchestra.org/wars-master/) for dev purposes only
- [16.12](https://packages.georchestra.org/bot/wars/16.12/) is the latest stable release (recommended)
- [15.12](https://packages.georchestra.org/bot/wars/15.12/) is the old stable


## Debian packages

We also provide a Debian repository.  
If you wish to use it, follow these steps:

 * Add the following line to your `/etc/apt/sources.list`,

replace `<version>` by the desired geOrchestra version (`16.12` for the current
stable version, `master` for the development version):

```
deb https://packages.georchestra.org/debian <version> main
```

 * Execute this one-liner:

For the master branch:

```
wget -O- https://packages.georchestra.org/debian/key.asc | apt-key add -
```

For the stable branch:

```
wget -O- https://packages.georchestra.org/debian/landry%40georchestra.org.gpg.pubkey | apt-key add -
```

 * Install the desired geOrchestra packages:

```
apt-get update && apt-get install georchestra-*
```

## YUM packages

To configure the repository, create a `/etc/yum.repos.d/georchestra.repo` file,
containing (replace `<version>` with `master`):

```
[georchestra]
name=geOrchestra repository
baseurl=https://packages.georchestra.org/yum/<version>
gpgcheck=1
gpgkey=https://packages.georchestra.org/yum/key.asc
```

Then, issue the following command:
```
yum install georchestra-*
```

## Other services

The following services are provided:

- [Maven repository](maven/)
- [Maven generated site](site/)
- [Jenkins CI (restricted access)](ci/)
- [Buildbot CI for stable branchs (restricted access)](bot/)

