# Installing the Windows Subsystem for Linux (WSL)

If you are running Windows 10 or Windows 11, you have the option of using Windows Subsystem for Linux.

## Requirements
- Windows install must be 64-bit
- CPU must support virtualization

## Installing WSL
WSL does not come enabled by default in Windows. You can enable it by:

1. Hit `Win + S` (open search)
2. Type `Turn Windows features on or off` and hit enter
3. Find `Windows Subsystem for Linux` in the listing, and tick the box next to it
4. Click the `OK` button
5. It will install and require a restart before it can be used.

## Installing a Linux Distro to WSL
Now that you have WSL, you can install a distro for it. Use the Microsoft Store app on Windows to install the distro.  
It's recommended that you install [Ubuntu](https://www.microsoft.com/store/productId/9NBLGGH4MSV6) or another Debian-based Linux distro.

## Using WSL
### Windows Terminal
If you do not already have Windows Terminal, which is packaged with newer versions of Windows 10 and 11, be sure to install it from the [Microsoft Store](https://www.microsoft.com/store/productId/9N0DX20HK701).

Windows Terminal is how you can use WSL. Open a new Windows Terminal and click the dropdown arrow next to the plus tab button. Select the `Ubuntu` option (or whatever distro you selected) and a new prompt tab should open. Here is where any commands in further guides/instructions would be entered.

### Accessing Home Directory
By default, Windows Terminal may start you out in a `/mnt/c/Users/YourUser` folder. Windows has mounted your regular OS drive to the Linux subsystem for ease of access and use. However, for the Linux-related things we will be doing, we can navigate to our home directory:
```sh
$ cd ~
```
Now, I recommend creating a directory to store your development efforts:
```sh
$ mkdir development
```
In that directory, you can then [clone the repo](downloading-aka-source-control.md) and [install/build it](installing.md).
