# Matomo template for OpenShift

Matomo is one of the open source web analytics platform.

## Deploy Matomo with new database

Use `matomo-mariadb.json`.

This template includes both of Matomo and MariaDB.

```sh
$ oc create -f matomo-mariadb.json
```

After this the "Matomo + MariaDB" template has shown in your catalog. Of course you can deploy from json directry without creating any template.

After deployiment, following objects had created:

* DeploymentConfig, ReplicationController, Pod
* Service
* Route
* ImageStream
* PersistentVolumeClaim
* Secret


## Deploy Matomo without new database

Use `matomo.json`.

This template include Matomo only. You have to have any existing compatible database (MySQL or MariaDB) for Matomo.

```sh
$ oc create -f matomo.json
```

After this the "Matomo" template has shown in your catalog. Of course you can deploy from json directry without creating any template.

After deployiment, following objects had created:

* DeploymentConfig, ReplicationController, Pod
* Service
* Route
* ImageStream
* PersistentVolumeClaim

## Note

Prease note: 

* Only HTTP (:80) has been configured. You have to modify your deployment if you want to use Matomo through HTTPS (:443).
* Cronjob for Matomo archiving is not included yet.
