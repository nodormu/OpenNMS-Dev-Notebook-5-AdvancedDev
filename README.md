additional features and the ALEC Machine Learning implementation installation

The advanced features are accessible via:  ssh -p 8101 admin@localhost
on the server the OpenNMS system is installed on.
This ssh session is after you are already logged on to the OpenNMS server itself via CLI.

For the ALEC/AI/Machine Learning installation text, I don't recommend using it in a production environment.
Nothing is affected and I have tested in a production environment of over 800 devices.
The postgresql database does not get corrupted, and none of the installed applications thus far:  postgres, opennms, grafana, elasticsearch and syslog-ng
have any issues whatsoever. The only problem is that on shutdown, whether manual, or using scripts as described in a previous Dev notebook on my github, 
the openNMS services hang on shutdown for exactly 5 minutes on the Jetty child process, crashes, then reboots as expected. 
All services come back up just fine, and I can't get any logs as to why it crashes. This has been an issue since ALEC was implemented in OpenNMS in version 24.x.
If you do decide to use ALEC in a production environment just keep this mind.