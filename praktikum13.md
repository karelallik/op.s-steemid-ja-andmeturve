Antud Praktikumi sooritasin enda isiklikus Windowsis. Praktikumi käigus sain algteadmised skriptimise kohta windowsis.
```
#$nr: 1

$outputFile = "c:\katse\tulemus-praktikum13.txt"

# Kogutav info
$hostname = (Get-ComputerInfo).CsName
$powershellVersion = $PSVersionTable.PSVersion.ToString()
$windowsVersion = (Get-ComputerInfo).OsName

# Tulemus stringina
$result = @"
Masina nimi: $hostname
PowerShelli versioon: $powershellVersion
Windowsi versioon: $windowsVersion
"@
# Kirjuta tulemused faili
$result | Out-File -FilePath $outputFile -Encoding UTF8 -Append

#$nr: 2

Get-WmiObject Win32_NetworkAdapterConfiguration -Filter "IPEnabled='True'" | 
    Select-Object IPAddress, IPSubnet, DefaultIPGateway, DHCPEnabled, MACAddress | 
    Format-Table -AutoSize | 
    Out-File -FilePath "c:\katse\tulemus-praktikum13.txt" -Encoding UTF8 -Append

#$nr: 3
#protsessori info
$processorInfo = Get-WmiObject Win32_Processor | 
    Select-Object Name, Manufacturer, MaxClockSpeed, NumberOfCores, NumberOfLogicalProcessors, Architecture 

# RAM suurus GB-des
$ramSizeGB = (Get-WmiObject Win32_ComputerSystem).TotalPhysicalMemory / 1GB

# Kirjutame tulemused faili
"$($processorInfo | Format-List | Out-String)`nRam: $([math]::round($ramSizeGB, 2)) GB" | Out-File "C:\katse\tulemus-praktikum13.txt" -Encoding UTF8 -Append

#$nr: 4
Get-WmiObject Win32_VideoController |
Select-Object Name, DriverVersion, DriverDate, CurrentHorizontalResolution |
Format-list |
Out-File -FilePath "C:\katse\tulemus-praktikum13.txt" -Encoding UTF8 -Append

#$nr: 5
# Kõvakettad (partitsioonitabel)
Get-WmiObject Win32_LogicalDisk | 
    Select-Object DeviceID, MediaType, Size, FreeSpace | 
    Format-Table -AutoSize |
    Out-File -FilePath $outputFile -Encoding UTF8 -Append

Get-WmiObject Win32_LogicalDisk |
    Select-Object DeviceID, MediaType, Size, FreeSpace |
    Where-Object { $_.DeviceID -eq "C:" } |
    ForEach-Object {
        $cDriveSizeGB = [math]::round($_.Size / 1GB, 2)  #aRVUTAB c: ketta mahtuvusee Gb-des      
        $cDriveFreeSpaceGB = [math]::round($_.FreeSpace / 1GB, 2) #arvutab C: ketta vaba ruumi GB-des
        "C:-kettal mahtuvus: $cDriveSizeGB GB, vaba ruum: $cDriveFreeSpaceGB GB" | 
        Out-File -FilePath $outputFile -Encoding UTF8 -Append
    }

#$nr: 6

Get-WmiObject –Class Win32_PnpSignedDriver | 
Where-Object {$_.DeviceID –like „PCI*“} | #filtreerib PCI seadmed
Select-Object Description, Manufacturer, DriverVersion | 
Sort-Object Description | #sorteerib kirjelduste järgi
Format-Table -Property Description, Manufacturer, DriverVersion -AutoSize | 
Out-File $outputFile -Encoding UTF8 -Append

#$nr: 7

Get-WmiObject -Class Win32_UserAccount |
Where-object { $_.LocalAccount -eq $true } | #filtreerib lokaalsed kasutajad
Select-Object Name, Description, LocalAccount, Disabled |
Format-Table -Property Name, Description, LocalAccount, Disabled -AutoSize |
Out-File -FilePath $outputFile -Encoding UTF8 -Append

#$nr: 8

$processCount = (Get-Process).Count #kogub käimasolevate protsesside arvu
"Protsesside arv: $processCount" | Out-File -FilePath $outputFile -Encoding UTF8 -Append

#$nr: 9

$last10Processes = Get-Process | 
    Select-Object Name, Id, StartTime |
    Sort-Object StartTime -Descending | #sorteerib protsessid käivitamise aja järgi
    Select-Object -First 10 #valib 10 viimast protsessi

"Viimased 10 käivitatud protsessi:" | Out-File -FilePath $outputFile -Encoding UTF8 -Append
$last10Processes | Format-Table -AutoSize | Out-File -FilePath $outputFile -Encoding UTF8 -Append

#$nr: 10

$currentDateTime = Get-Date #saab arvuti kuupäeva ja kellaaja
"Arvuti kuupäev ja kellaaeg: $currentDateTime" | Out-File -FilePath $outputFile -Encoding UTF8 -Append
```
