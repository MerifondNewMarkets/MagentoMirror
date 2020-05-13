# MagentoMirror

This repository contains some mirrored Magento releases since they are f***ing hard to download. The sample files that are freely available and installable via `n98-magerun.phar` (which is a great project, btw.) take forever to download. They are hosted on SourceForge and I guess they artificially throttle the download speed?

Anyway, these files may be used within `n98-magerun.phar` by adding the file `.n98-magerun.yaml` to your home folder:

```yaml
commands:
  N98\Magento\Command\Installer\InstallCommand:
    magento-packages:
      - name: magento-mymirror-1.9.4.5
        version: 1.9.4.5
        dist:
          url: https://github.com/MerifondNewMarkets/MagentoMirror/releases/download/v1.9.4.5/magento-1.9.4.5.tar.gz
          type: tar
        extra:
          sample-data: sample-data-mymirror-1.9.2.4

    demo-data-packages:
      - name: sample.data-mymirror-1.9.2.4
        version: 1.9.2.4
        dist:
          url: https://github.com/MerifondNewMarkets/MagentoMirror/releases/download/v1.9.4.5/sample-data-1.9.2.4.tar.gz
          type: tar
```
