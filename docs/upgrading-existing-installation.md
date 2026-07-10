# Upgrading an Existing Installation


## Upgrade Prerequisites

Before running the new installer, you must manually stop the service and back up your existing software data to prevent any data loss.

### 1. Stop the Windows Service
Open the Windows Services manager (`services.msc`), locate **OOGy 2.0**, right-click it, and select **Stop**.

### 2. Back Up Configuration Data
Locate and copy the following configuration directory to a safe backup location on your machine:
`C:\ProgramData\Oracular\OOGy`

### 3. Back Up Installation Files
Locate and copy your current software installation directory. If you used the standard setup, the default location is:
`C:\Program Files\OOGy`


## Key Upgrade Steps

### Process Detection
The new installation wizard will automatically detect your existing application pathway.

### Data Preservation
Your manually created backup folders ensure that your historical connection strings and logs remain safe during the overwriting process.

### Post-Installation File Restorations
After completing the installation, you must restore your original configuration settings:
1. Navigate to `C:\ProgramData\Oracular\OOGy`.
2. Replace the newly installed `application.properties` and `Config.yaml` files with your original backup files.
3. Open `application.properties` and verify that the `server.port` value (e.g., `8081`) exactly matches the port assigned to the OOGy website in Internet Information Services (IIS).

### Service Restarts
Once the files are replaced and the port is verified, restart the system components to apply changes:
1. Open the Windows Services manager and restart the **OOGY2.0** service.
2. Open the IIS Manager, locate the **OOGy** website under the Connections pane, and restart the service.