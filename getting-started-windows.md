# Getting Started - Windows

### Prerequisites <a href="#gettingstarted-windows-prerequisites" id="gettingstarted-windows-prerequisites"></a>

1. Windows
   1. Windows 10 Enterprise or later, Windows Server 2016 or later
   2. Permission to "Run as Administrator" for the installer
2. 64-bit processor, 2.90GHz
3. 32 GB Installed memory (RAM)
4. DataConnect v12 License file (typically \*.slc)

### What Will Be Installed <a href="#gettingstarted-windows-whatwillbeinstalled" id="gettingstarted-windows-whatwillbeinstalled"></a>

1. Actian Integration Manager (Windows Service)
2. Actian Integration Manager Worker (Windows Service, optional usage)
3. Actian Messaging Broker (Windows Service, optional usage)
4. Actian File Folder Listener (Windows Service, optional usage)
5. DataConnect v12 Embedded Engine
6. AdoptJDK 11 Embedded JRE

### Installation <a href="#gettingstarted-windows-installation" id="gettingstarted-windows-installation"></a>

1. Download Actian Integration Manager from [https://esd.actian.com/](https://esd.actian.com/).
2. Right click the downloaded installer file (integration-manager-xxx-win.exe) and select "Run as administrator".
3. If you have a previous 3.x.x version installed, you will be coerced to uninstall first. Uninstall will shutdown running services and prepare for library updates, it will NOT remove or alter ProgramData (conf files, logs, etc...).
4. Accept the License Agreement.
5. Select the installation path (default: C:/Program Files/Actian/IntegrationManager).
6. Select the shared data path (default: C:/ProgramData/Actian/IntegrationManager).
7. Installation should take less than a minute.

### Configuration/Reconfiguration <a href="#gettingstarted-windows-configuration-reconfiguration" id="gettingstarted-windows-configuration-reconfiguration"></a>

1. Locate the application.properties file (default: C:/ProgramData/Actian/IntegrationManager/conf/application.properties)
2. Note that if you have a previous installation of Integration Manager, none of your existing property values will be changed.&#x20;
3. You can confirm or alter the path to your DataConnect v12 license file using the property "engine.licensePath" (default: C:/ProgramData/Actian/IntegrationManager/license/dc12.slc).
   1. If you were previously using Integration Manager v2 and DataConnect v11, you will need to alter this value before executing any integrations. DataConnect v11 and v12 licenses are not interchangeable.
4. You can also run Integration Manager on a different port using the property "server.port" (default: 8080).
5. The application.properties file can be used for a variety of configurations to tailor Integration Manager to your requirements and environment. See the Advanced Use Cases documentation for a description of available properties.
6. ANY change to the application.properties file will require a restart of the service.
   1. Go to Windows → Administrative Tools → Services.
   2. Right click on Actian Integration Manager to stop, start, or restart.
7. Remember that configuration file changes will survive uninstallation/reinstallation.

### Run Your First DJAR <a href="#gettingstarted-windows-runyourfirstdjar" id="gettingstarted-windows-runyourfirstdjar"></a>

1. Navigate to [http://localhost:8080/ui/](http://localhost:8080/ui/) in your web browser. If installed on a network server, open http://\_SERVER\_NAME\_:8080/ui/.
2. On the login page, enter the default user credentials (admin/admin). You can change the password in User Administration (highly recommended).
3. IM opens on the Dashboard page, from here navigate to the Configurations tab.
4. Click +Add.
5. Setup a new Configuration:
   1. Give it a unique Name.
   2. Click Add Package.
   3. Upload a DataConnect djar file.
   4. Select an Entry Point within the djar.
   5. Click on the Macros sub-tab.
   6. Add and/or import any macros your djar requires.
6. Click Run Configuration.
7. Navigate to the Jobs sub-tab to view job progress and log file.

### Service Logs & Monitoring <a href="#gettingstarted-windows-servicelogs-and-monitoring" id="gettingstarted-windows-servicelogs-and-monitoring"></a>

1. You can monitor service activity and get important additional information from the log file (default:  C:/ProgramData/Actian/IntegrationManager/logs/IntegrationManager.log)
2. You can retrieve DataConnect Engine log files by Job Id in the job history folder (default: C:/ProgramData/Actian/IntegrationManager/history/job)
3. Remember that log file data will survive uninstallation/reinstallation.&#x20;
