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

	Run Grafana PDC agent as a Windows Service
1. Add PDC.exe binary under Grafana Agent Folder
2. Download and drop the NSSM binary folder under the grafana agent/pdc folder as well. The NSSM program helps create the windows service.
i. 
ii. Using NSSM to create the services and run the bat file that includes the string arguments. 
	1) Run NSSM to configure and create a service. 
	2) c:\Program Files\Grafana Agent\pdc\nssm-2.24\win64>nssm install "Grafana PDC"
	3) You can change the name of the service to whatever you choose. Optional commands to edit the service after the fact:
		a) >NSSM edit "Grafana PDC"
	
	4) 
	
	5) 
	6) 


iii. Start the service for the first time. This will create SSH certs here : C:\Windows\System32\config\systemprofile\.ssh
	1) NOTE: Following these instructions did not make me have to modify the Cert permissions below but when testing.
	2) 2nd NOTE: This cert that it uses will need to have modified permissions if Grafana still does not show CONNECTED like this:
iv. 

	1) 
	
	2) 
	3) If this is NOT done the service will run just fine but the error log will show this:
		@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
		@         WARNING: UNPROTECTED PRIVATE KEY FILE!          @
		@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
	4) Batch file the service runs:
		a) "C:\Program Files\Grafana Agent\pdc\pdcstart.bat"
		b)  Example Bat file command and arguments
pdc.exe -token ADD YOUR TOKEN HERE  -cluster prod-us-east-0 -gcloud-hosted-grafana-id YOUR GRAFANA ID ![image](https://github.com/EricSchroeder12/Grafana-pdc-agent/assets/16087194/305d4074-f7e0-4c5a-bfec-7c53e3387f88)
		
