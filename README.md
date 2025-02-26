# pdc-agent

The Grafana Private Datasource Connect Agent allows connecting private datasources with your grafana cloud instance.


## Installation

Follow installation and running instructions in the [Grafana Labs Documentation](https://grafana.com/docs/grafana-cloud/data-configuration/configure-private-datasource-connect/)



## Releasing
Create public releases with `gh release create vX.X.X --generate-notes

Releases are managed using [goreleaser](https://goreleaser.com/). Use the following command to build binaries on your local machine.

```
goreleaser build --snapshot --rm-dist
```

If you want the docker image locally, you can run

```
goreleaser release --snapshot --rm-dist
```

Installing PDC Grafana Agent as a windows service
 ![image](https://github.com/EricSchroeder12/Grafana-pdc-agent/assets/16087194/305d4074-f7e0-4c5a-bfec-7c53e3387f88)
		
