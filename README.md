# pcl-6-download-
PS script to download hp pcl drivers and open in temp folder for quick disposal

# Define the download URL for the HP Universal PCL6 Driver
$driverUrl = 'https://ftp.hp.com/pub/softlib/software13/COL40842/ds-99374-24/upd-pcl6-x64-7.0.1.24923.exe'

# Define the download path for the driver
$tempFolder = [System.IO.Path]::GetTempPath()
$fileName = 'upd-pcl6-x64-7.0.1.24923.exe'
$downloadPath = Join-Path $tempFolder $fileName

# Download the driver from the URL
Invoke-WebRequest -Uri $driverUrl -OutFile $downloadPath

# Install the driver silently
Start-Process $downloadPath -ArgumentList '/s' -Wait
