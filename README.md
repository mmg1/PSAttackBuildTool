## PS>Attack

A platform for generating a portable powershell attack environment (from [PSPunch](https://www.github.com/jaredhaight/PSPunch/)). The generated environment is a self contained exe and comes with a lot of the latest and greatest offensive PowerShell tools. 

#### What does it do?
PS>Attack handles downloading PSPunch, downloading updated versions of the modules that it uses (PowerSploit, PowerTools, etc), encrypts them with a unique key and then packages everything up into a self contained exe.

#### What is PSPunch?
[PSPunch](https://www.github.com/jaredhaight/PSPunch/) is used by PS>Attack to generate the portable attack environment. PSPunch combines some of the best projects in the offensive powershell community into a self contained executable. It uses a couple of techinques to evade antivirus and Incident Response teams.

1. It doesn't rely on powershell.exe. Instead it calls powershell directly through the dotNet framework.
2. The modules that are bundled with the exe are encrypted. When PSPunch starts, they are decrypted into memory. The unencrypted payloads never touch disk, making it difficult for most antivirus engines to catch them.
2a. When generated by PS>Attack, the payloads are encrypted with a unique key. This means that the generated executable's signature changes each time it's created. 

Offensively, PSPunch contains commands for Privilege Escalation, Recon and Data Exfilitration.

PSPunch includes the following modules and commands preinstalled and ready to go:
* [Powersploit](https://github.com/PowerShellMafia/PowerSploit)
  - Invoke-Mimikatz
  - Invoke-GPPPassword
  - Invoke-NinjaCopy
* [PowerTools](https://github.com/PowerShellEmpire/PowerTools)
  - PowerUp
  - PowerView

#### Thanks and Ackwnowledgements
PS>Attack was inspired by and benefits from a lot of incredible people in the PowerShell community. Particularly [mattifiestation](https://twitter.com/mattifestation) of PowerSploit and [sixdub](https://twitter.com/sixdub), [engima0x3](https://twitter.com/enigma0x3) and [harmj0y](https://twitter.com/HarmJ0y) of Empire. Besides writing the modules and commands that give PSPunch it's.. punch, their various projects have inspired alot of my approach to PSAttack and PSPunch as well as my decision to try and contirbute something back to the community.
