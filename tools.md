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

