# MagentoMirror

This repository contains some mirrored Magento releases since they are f***ing hard to download. The sample files that are freely available and installable via `n98-magerun.phar` (which is a great project, btw.) take forever to download. They are hosted on SourceForge and I guess they artificially throttle the download speed?

Anyway, these files may be used within `n98-magerun.phar` by adding the file `.n98-magerun.yaml` to your home folder:

```yaml
commands:
  N98\Magento\Command\Installer\InstallCommand:
    magento-packages:
      - name: magento-merifondnewmarkets-1.9.4.5
        version: 1.9.4.5
        dist:
          url: https://github.com/MerifondNewMarkets/MagentoMirror/releases/download/v1.9.4.5/magento-1.9.4.5.tar.gz
          type: tar
        extra:
          sample-data: sample-data-merifondnewmarkets-1.9.2.4

    demo-data-packages:
      - name: sample.data-merifondnewmarkets-1.9.2.4
        version: 1.9.2.4
        dist:
          url: https://github.com/MerifondNewMarkets/MagentoMirror/releases/download/v1.9.4.5/magento-sample-data-1.9.2.4.tar.gz
          type: tar
```

With this file in place inside your home folder you can do install Magento like this:

```bash
n98-magerun.phar install \
    --magentoVersionByName="magento-merifondnewmarkets-1.9.4.5" \
    --installationFolder="$MAGENTO_WEBROOT" \
    --dbHost="$MYSQL_HOST" \
    --dbUser="$MYSQL_USER" \
    --dbPass="$MYSQL_PASSWORD" \
    --dbName="$MYSQL_DATABASE" \
    --baseUrl="$MAGENTO_BASEURL" \
    --installSampleData="y" \
    --useDefaultConfigParams="y"
```

> Replace the variables with your actual values.
