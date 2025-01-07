<h1 align="center">
  <br>
  <a href=""><img src="/img/logo.webp" alt="" width="400px;"></a>
  <br>
  <img src="https://img.shields.io/badge/PRs-welcome-blue">
  <img src="https://img.shields.io/github/last-commit/kh4sh3i/WSL">
  <img src="https://img.shields.io/github/commit-activity/m/kh4sh3i/WSL">
  <a href="https://twitter.com/intent/follow?screen_name=kh4sh3i_"><img src="https://img.shields.io/twitter/follow/kh4sh3i_?style=flat&logo=twitter"></a>
  <a href="https://github.com/kh4sh3i"><img src="https://img.shields.io/github/stars/kh4sh3i?style=flat&logo=github"></a>
</h1>

# WSL
WSL (Windows Subsystem for Linux) allows developers to run a Linux environment directly on Windows without the need for a virtual machine or dual boot setup. It enables running Linux tools, utilities, and applications alongside Windows applications.

Key Features of WSL:
Run Linux distributions like Ubuntu, Debian, Kali Linux, and others.
Access Linux command-line tools like bash, ssh, grep, and awk directly on Windows.
Share files between Linux and Windows seamlessly.
Install software using Linux package managers like apt or yum.



# Steps to Install WSL:
1. Enable WSL on Windows:

* Open PowerShell as Administrator.
* Run the command:
```
wsl --install
wsl --set-default-version 2
```

This installs WSL 2 (the latest version) and sets it as the default version.


2. Install a Linux Distribution:

After installation, restart your computer if prompted.
Open the Microsoft Store, search for a Linux distribution (e.g., Ubuntu), and install it.
Launch the distribution from the Start menu to initialize it.

3. Verify Installation:

Open a terminal and run:
```
wsl --list --verbose
```

This will show the installed distributions and their WSL versions.

4. Update WSL (Optional):
```
wsl --update
```

## manual install WSL on offline system
```
Step 1 - Enable the Windows Subsystem for Linux
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart

Step 2 - Enable Virtual Machine feature
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart

Step 3 - Download the Linux kernel update package
https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi

Step 4 - Set WSL 2 as your default version
wsl --set-default-version 2

//online install 
Invoke-WebRequest -Uri https://aka.ms/wslubuntu2004 -OutFile Ubuntu.appx -UseBasicParsing
```

## export & import WSL


Step 1: Export WSL Instance from the Old System
```
wsl --list --verbose
wsl --export <DistributionName> <PathToSave>\<FileName>.tar
wsl --export Ubuntu-20.04 D:\Backup\Ubuntu-20.04.tar
```


Step 2: Enable WSL on the New System
```
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
install wsl_update_x64.msi
```


Step 3: Import WSL Instance on the New System
```
wsl --import <DistributionName> <InstallLocation> <PathToTarFile>
wsl --import Ubuntu-20.04 D:\WSL\Ubuntu-20.04 D:\Backup\Ubuntu-20.04.tar
wsl --list --verbose
```

## refrences
* [wsl microsoft](https://learn.microsoft.com/en-us/windows/wsl/install-manual)

