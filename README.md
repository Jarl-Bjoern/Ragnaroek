<h1 align="center">💀 Yggdrasil 💀</h1>
<p align="center"></p>
<div align="center">
  <a href="https://www.kali.org/">
    <img alt="linux" src="https://svgshare.com/i/Zhy.svg" />
  </a>
  <a href="https://www.python.org/downloads/release/python-3100/">
    <img alt="python" src="https://img.shields.io/badge/python-3.10-blue.svg" />
  </a>
  <a href="https://visitor-badge.glitch.me/badge?page_id=jarl-bjoern/yggdrasil&left_color=grey&right_color=blue">
    <img alt="visitors" src="https://visitor-badge.glitch.me/badge?page_id=jarl-bjoern/yggdrasil&left_color=grey&right_color=blue" />
  </a>
  <a href="https://GitHub.com/jarl-bjoern/yggdrasil/releases/">
    <img alt="releases" src="https://img.shields.io/github/downloads/Naereen/StrapDown.js/total.svg" />
  </a>
  <a href="https://github.com/jarl-bjoern">
      <img title="Follower" src="https://img.shields.io/github/followers/Jarl-Bjoern.svg?style=social&label=Follow&maxAge=2592000"><a href="https://github.com/Jarl-Bjoern?tab=followers"></a>
</div>
<div align="center">
  <a href="https://www.python.org/">
    <img alt="python" src="https://img.shields.io/badge/Made%20with-Python-1f425f.svg" />
  </a>
  <a href="https://www.gnu.org/software/bash/">
    <img alt="bash" src="https://img.shields.io/badge/Made%20with-Bash-1f425f.svg" />
  </a>
    <a href="https://www.gnu.org/software/bash/">
    <img alt="powershell" src="https://img.shields.io/badge/Made%20with-PowerShell-1f425f.svg" />
  </a>
</div><br/>

This tool is intended to simplify the setup of various tools and configuration of a Kali machine after a fresh installation and save unnecessary time, so that a predefined list can be used in advance or you can also create your own.<br />

The name `Yggdrasil` comes from Norse mythology and is the tree of life or world tree, here the name is quite appropriate for the concept of the program, as it is geared for several pentetration test areas or even for digital forensics.<br />

## ❗ News
<strong>Upcoming changes for version</strong> `0.9`:
  - new cleaning task for old container images inside the updater settings
  - automated installer for firefox extensions
  - new installation categories was added
  - automated and manual updater for the cargo tools
  - new parameter was added to show interaction messages during the apt installation
  - reorganization of the repository
  - new menu for the best practice settings like vim configuration, crontab etc.
  - automated updater for the git tools
  - ability to choose your own installation directory
  - colorized information after the installation
  - manual update alias for the installed git tools and microcode update
  - added automated shredding task after 90 days for data privacy
  - updated README
  - added hardening options for apache and nginx
  - new colors was added
  - the python files have been split up
  - logging bug fixes
  - bug and logical fixes

<div align="center">
➡️ <a href="https://github.com/Jarl-Bjoern/Yggdrasil/blob/main/Information/Changelog/full.md">
  Full Changelog
</a> ⬅️
</div><br />

## 📃 Settings overview
- Ability to configure your own setting
  - Changing the default installation path to your own
  - Custom config based on the provided template
  - Include a custom path of your own scripts or dpkg packages
- Automation download of tools from the following categories
  - APT
  - Cargo
  - Custom Websites (via wget)
  - Docker
  - Gem
  - Go
  - pip
- Best Practice settings
  - Automated Updater via Crontab
    - Docker Images
    - GIT Tools
    - Important pip packages
    - Cargo Tools
    - OS
  - Autmated cleaning tasks
    - shredding script to remove your penetration test results after 90 days for privacy reasons
    - cleaning script to remove old container images
  - Changing the default hostname
  - Custom configuration
    - Alias
      - base64 function
      - colorized grep
      - human readable df & du commands
      - manual microcode update
      - manual git tools update
      - nmap exclude for local ip addresses
    - BASHRC and ZSHRC
    - Screenrc
    - VIM
  - Repository change from rolling-release (bleeding-edge) to last-snapshot
  - Overview about some useful information after the install
- GUI automation
  - accept licenses
  - install firefox extensions
- Hardening
  - Apache
  - Firewall
  - Kernel
  - nginx
  - SSH

# 📖 Table of Contents
- [How to download and install the tool](#download_install)
  - [Preparations](#preparation_install)
  - [Download and start the tool](#start_install)
  - [Using the help section to see which parameters do we have](#help_install)
  - [Choose one of the three category types](#category_install)
  - [Choose between one of the Pentesting categories](#pentesting_install)
  - [Choose between multiple Pentesting categories](#pentesting_multiple_install)
  - [Choose one of the two installation types](#type_install)
  - [Choose between multiple hardening options](#hardening_install)
  - [Configurate your SSH IP-Address](#ssh_install)
  - [Choose between the provided best practice settings](#best_practice_settings)
- [Using the automated variant](#automated_install)
- [Customize your installation](#custom_install)
  - [Method Example](#method_install)
  - [Build from scratch](#custom_install_II)
  - [Include Customized Scripts](#directory_install)

<a name="download_install"></a>
# ⚔ How to download and install the tool

<a name="preparation_install"></a>
## ⚔ Preparations
The tool `dos2unix` is needed to be able to format all the files of the program into the correct format. 
```bash
sudo apt install -y dos2unix
```

If you want to use the provided GUI automation, make sure that the `scrot` tool is installed.
```
sudo apt install -y scrot
```

<strong>Notice:</strong> In some cases, you may need to restart the Kali machine once after the preparations.

<a name="start_install"></a>
## ⚔ Download and start the tool
```bash
sudo git clone https://github.com/Jarl-Bjoern/Yggdrasil/
cd Yggdrasil
sudo python3 yggdrasil.py
```

<a name="help_install"></a>
## ⚔ Using the help section to see which parameters do we have
```python
usage: yggdrasil.py [-aL [ACCEPT_LICENSES]] [-aW ADD_WORKSPACE] [-hN HOST_NAME] [-p PATH]
                    [-sC [SKIP_CONFIG]] [-sH [SKIP_HARDENING]] [-tP TOOL_PATH]
                    [-v [VERBOSE]] [-h]

optional arguments:
  -aL [ACCEPT_LICENSES], --accept-licenses [ACCEPT_LICENSES]
                        This parameter is required to accept licenses and the popups from firefox
                        during the installation of extensions.

                        Extensions:
                          - Firefox

                        Licenses:
                          - Veracrypt

                        ---------------------------------------------------------------
  -aW ADD_WORKSPACE, --add-workspace ADD_WORKSPACE
                        This parameter specifies your default workspace location.

                        Default: /opt/workspace

                        ---------------------------------------------------------------
  -hN HOST_NAME, --host-name HOST_NAME
                        This parameter specifies the hostname of the kali machine.

                        Default:
                          - pentest-kali
                          - forensic-kali

                        ---------------------------------------------------------------
  -p PATH, --path PATH  This parameter specifies the target path of your custom tools.
                                                                                                                                                                                                                                            
                        Example:
                          - python3 yggdrasil.py -p /opt/yggdrasil/Custom

                        ---------------------------------------------------------------
  -sC [SKIP_CONFIG], --skip-config [SKIP_CONFIG]
                        This parameter skips the configs part.

                        Best practice settings:
                          - Automated Updates (APT|Docker|Git Packages|Pip)
                          - Custom Configs (alias|bashrc|zshrc)
                          - screenrc
                          - vim
                          - repo-change (rolling-release to last-snapshot)

                        ---------------------------------------------------------------
  -sH [SKIP_HARDENING], --skip-hardening [SKIP_HARDENING]
                        This parameter skips the hardening part.

                        Hardening:
                          - Firewall
                          - Operating System
                          - SSH
                          - Apache
                          - nginx

                        ---------------------------------------------------------------
  -tP TOOL_PATH, --tool-path TOOL_PATH
                        This parameter specifies your default tools location.

                        Default:
                          - /opt/pentest_tools
                          - /opt/forensic_tools

                        ---------------------------------------------------------------
  -v [VERBOSE], --verbose [VERBOSE]
                        This parameter shows all interaction messages during the apt
                        package manager installation process.

                        ---------------------------------------------------------------
```

<a name="category_install"></a>
## ⚔ Choose one of the three category types
```bash
💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀
💀                                                       💀
💀                       Yggdrasil                       💀
💀                     Version 0.9                       💀
💀           Rainer Christian Bjoern Herold              💀
💀                                                       💀
💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀


          Please choose between one category
----------------------------------------------------------
|                                                        |
| [1] complete    :   installation of both toolkits      |
| [2] custom      :   installation of custom tools       |
| [3] forensic    :   installation of forensic tools     |
| [4] pentest     :   installation of pentest tools      |
| [5] hardening   :   installation of hardening tools    |
| [6] cloud       :   installation of cloud-pentesting   |
|                     tools                              |
| [7] training    :   installation of training tools     |
|                                                        |
----------------------------------------------------------

Your Choice: pentest
```

<a name="pentesting_install"></a>
## ⚔ Choose between one of the Pentesting categories
```bash
💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀
💀                                                       💀
💀                       Yggdrasil                       💀
💀                     Version 0.7b                      💀
💀           Rainer Christian Bjoern Herold              💀
💀                                                       💀
💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀


          Please choose between one category
----------------------------------------------------------
|                                                        |
| [1] infrastructure  :   tools for infra pentesting     |
| [2] iot             :   tools for iot pentesting       |
| [3] mobile          :   tools for mobile pentesting    |
| [4] red_teaming     :   tools for red teaming          |
| [5] web             :   tools for web pentesting       |
|                                                        |
----------------------------------------------------------

Your Choice: infrastructure
```

<a name="pentesting_multiple_install"></a>
## ⚔ Choose between multiple Pentesting categories
```bash
💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀
💀                                                       💀
💀                       Yggdrasil                       💀
💀                     Version 0.7g                      💀
💀           Rainer Christian Bjoern Herold              💀
💀                                                       💀
💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀


          Please choose between one category
----------------------------------------------------------
|                                                        |
| [1] infrastructure  :   tools for infra pentesting     |
| [2] iot             :   tools for iot pentesting       |
| [3] mobile          :   tools for mobile pentesting    |
| [4] red_teaming     :   tools for red teaming          |
| [5] web             :   tools for web pentesting       |
|                                                        |
----------------------------------------------------------

Your Choice: 1,5
```

<a name="type_install"></a>
## ⚔ Choose one of the two installation types
```bash
💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀
💀                                                       💀
💀                       Yggdrasil                       💀
💀                     Version 0.7b                      💀
💀           Rainer Christian Bjoern Herold              💀
💀                                                       💀
💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀


          Please choose between one installation
----------------------------------------------------------
|                                                        |
|  [1]       full    : full    installation (GUI)        |
|  [2]       minimal : minimal installation (CLI)        |
|                                                        |
----------------------------------------------------------

Your Choice: full
```

<a name="hardening_install"></a>
## ⚔ Choose between multiple hardening options
```bash
💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀
💀                                                       💀
💀                       Yggdrasil                       💀
💀                     Version 0.8                       💀
💀           Rainer Christian Bjoern Herold              💀
💀                                                       💀
💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀

----------------------------------------------------------
|                                                        |
| [1] complete         :   complete configuration        |
| [2] Firewall         :   firewall                      |
| [3] Sysctl (OS)      :   sysctl hardening              |
| [4] SSH              :   SSH hardening                 |
| [5] Apache           :   Apache hardening              |
| [6] nginx            :   nginx hardening               |
|                                                        |
----------------------------------------------------------

Your Choice: 1
```

<a name="ssh_install"></a>
## ⚔ Configurate your SSH IP-Address
```bash
💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀
💀                                                       💀
💀                       Yggdrasil                       💀
💀                     Version 0.8                       💀
💀           Rainer Christian Bjoern Herold              💀
💀                                                       💀
💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀


           Please select an IP address to be used
                   for SSH configuration
----------------------------------------------------------

     eth0: 
       -  192.168.56.2 (IPv4)
       -  fe80::XXX:XXXX:XXXX:XXXX (IPv6)
----------------------------------------------------------

Your Choice: 192.168.56.2

```

<a name="best_practice_settings"></a>
## ⚔ Choose between the provided best practice settings
```bash
💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀
💀                                                       💀
💀                         Yggdrasil                     💀
💀                        Version 0.9                    💀
💀              Rainer Christian Bjoern Herold           💀
💀                                                       💀
💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀💀


-----------------------------------------------------------
|                                                         |
|  [1] complete      :   complete configuration           |
|  [2] updates       :   automated updates                |
|                        (APT|Docker|Git Packages|Pip)    |
|  [3] alias         :   custom configs                   |
|                        (alias|.bashrc|.zshrc)           |
|  [4] screenrc      :   custom screenrc config           |
|  [5] vim           :   custom vim config                |
|  [6] repo          :   kali repository change           |
|                                                         |
-----------------------------------------------------------

Your Choice: 1
```

<a name="automated_install"></a>
## ⚔ Using the automated variant
```bash
# Automated Variant text based without Hardening
cat <<EOF | sudo python3 /opt/Yggdrasil/yggdrasil.py -sH
pentest
infrastructure
full
complete
EOF

# Automated Variant without Hardening with numbers
cat <<EOF | sudo python3 /opt/Yggdrasil/yggdrasil.py -sH
4
1
1
1
EOF

# Automated Variant with multiple pentesting categories without Hardening with numbers
cat <<EOF | sudo python3 /opt/Yggdrasil/yggdrasil.py -sH
4
1,5
1
EOF
```

<br /><strong>Notice:</strong> Make sure that if you use the Complete installation from Hardening part, that you also specify the IP address for the SSH server, otherwise you will end up in an exception.
```bash
# Automated Variant with multiple pentesting categories text based
cat <<EOF | sudo python3 /opt/Yggdrasil/yggdrasil.py
pentest
infrastructure,web
complete
192.168.2.1
complete
EOF

# Automated Variant with multiple pentesting categories with numbers
cat <<EOF | sudo python3 /opt/Yggdrasil/yggdrasil.py
4
1,5
1
192.168.2.1
1
EOF
```

<a name="custom_install"></a>
# 📝 Customize your installation
You can open up one of the configuration files and add your own tools to the list to customize it to your liking (Make sure that the heading must always begin with a `#`).

In this example we take the configuration file for `infrastructure penetration testing`, which can be found under the following path `Config/Linux/Pentest/Infrastructure/minimal.txt`

<strong>Notice:</strong> The `minimal.txt` is set for special installation, e.g. if you are designing internal penetration tests remotely and can only connect to your target system via SSH and have no way to use GUI-based applications unless X11 forwarding is available.

After opening the file `minimal.txt` with an editor of your choice, you will now see a number of tools that have already been defined for various package managers.

```bash
# APT
bloodhound
dhcpig
fcrackzip

...
```

In this example we add the tool `Feroxbuster` under the header `#APT`, now at the next start the added tool will be installed.

<strong>Notice:</strong> When inserting new tools, make sure that you add it to the correct section of the respective package manager.

```bash
# APT
bloodhound
dhcpig
fcrackzip
feroxbuster

.....
```
Now you can add more tools as you wish.

When you arrive at the `Wget` section, you need to see that they follow the structure below.
```
URL Name Method
```
1. Insert a `URL` in the `first position` and make sure that the links can be called with a direct download and are not provided with a timer.
2. Note the `name` of the program to the `second place`, this is necessary that the file is named with a simpler name during the download and thus it is also easier to filter.
3. In the `third place` now follows the `method`, what kind of format the file has and how the program should behave, for example to unpack an archive. A detailed list of the available methods follows in the next chapter.

<a name="method_install"></a>
## 📝 The following methods are available:
### Archive
With the `Archive` argument you specify that you are downloading an archive, which is then loaded into the provided Python script and unpacked.
```bash
# Wget
https://dl.pstmn.io/download/latest/linux64 Postman Archive
```
### DPKG
The argument `DPKG` is used to download a package, which will be imported/installed afterwards.
```bash
# Wget
https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb chrome DPKG
```
### Executeable
With `Executeable`, you specify that you are downloading an executable file that is for example downloadable via Github like kerbrute.
```bash
# Wget
https://github.com/ropnop/kerbrute/releases/download/v1.0.3/kerbrute_linux_amd64 kerbrute Executeable
```
### Installer
The `Installer` argument specifies that you download an installation package like .msi, which is subsequently launched, as is done with the Soap UI ready, for example, if you use the template for web penetration testing.
```bash
# Wget
https://sh.rustup.rs rust Installer
```
### Extension
With the `Extension` argument you specify that a browser addon should be installed. This has already been implemented for the Web Penetration Testing Template, for example.

<strong>Notice:</strong> Currently this is only possible for Firefox.
```bash
# Wget
https://addons.mozilla.org/android/downloads/file/3616824/foxyproxy_standard-7.5.1.xpi foxyproxy Extension
```

<a name="custom_install_II"></a>
## 📝 Build from scratch
You can also build the file from scratch yourself. To do this, navigate to the directory `Config/Linux/Custom` and edit the file `install.txt`
```bash
# APT

# Cargo

# Docker

# Gem

# Git

# Go

# Python

# Wget

# Wordlists
```

<a name="customized_scripts"></a>
## 📝 Include Customized Scripts
In addition, it is also possible that you can place your own scripts or packages in the provided `Custom` directory or your own directory and use them in the installation script.

For this, you must use the parameter `-p` in combination with the absolute path, as in the example below

<strong>Currently the following formats are available to install external scripts or packages:</strong>
  - Bash/Shell
  - DPKG

<a name="directory_install"></a>
## Example
```bash
python3 /opt/Yggdrasil/yggdrasil.py -p /mnt/MY_DIRECTORY
```

# 🏆 Special thanks
In the context of the development of the tool, I would like to thank the following people for their contribution:
  - atreus92
  - cddmp
  - Explie
  - GhostActive
  - HomeSen
  - ikstream
  - janstarke
  - julion-m
  - pyxon73
  - SandySchoene
  - SecMyth

# ⚠️ Remark
It should be said that the scripts are still under development, but already allow an easier start to perform as a penetration tester or digital forensics, certain pre-settings.
