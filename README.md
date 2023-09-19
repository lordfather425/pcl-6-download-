# pcl-6-download-
PS script to download hp pcl drivers and open in temp folder for quick disposal




# Copy and paste or just download .ps1 and run in powershell
$driverUrl = 'https://ftp.hp.com/pub/softlib/software13/COL40842/ds-99374-24/upd-pcl6-x64-7.0.1.24923.exe'

$tempFolder = [System.IO.Path]::GetTempPath()

$fileName = 'upd-pcl6-x64-7.0.1.24923.exe'

$downloadPath = Join-Path $tempFolder $fileName

Invoke-WebRequest -Uri $driverUrl -OutFile $downloadPath

Start-Process $downloadPath -ArgumentList '/s' -Wait
