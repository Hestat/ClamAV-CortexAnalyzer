# ClamAV-Analyzer

Analyzer for integrating ClamAV scanning to TheHive and Cortex.

When investigating an incident you may not want to send a file off to Virustotal or some other public resource.

ClamAV will allow you to scan locally, and you can add custom rules to ClamAV via Sigtool and Yara to enhance its detection capability.

Package includes everthing you will need to setup in TheHive

	pyclam_analyzer.py
	clam.json

	Templates:
	long.html
	short.html

Python package requirements:

	cortexutils
	os
	pyclamd

## However! Keep reading

You  will need to have Clamd installed and running on the server that TheHive/Cortex is running on so that it can connect for the scans.

As well you will need to make som adjustments to the user and/or group running Clamd by default Clamd runs as the clamav user, you will need to allow root, or edit the config to allow additional groups to clamd as the observables that TheHive will send to the scanner will be owned by the cortex user.
