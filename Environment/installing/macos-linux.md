# Installing on macOS or Linux (debian-based)
These will compile and run on [Apple silicon](https://en.wikipedia.org/wiki/Apple_silicon), [Intel](https://en.wikipedia.org/wiki/List_of_Intel_CPU_microarchitectures), and [AMD](https://en.wikipedia.org/wiki/List_of_AMD_processors) chips.
This also works on the [Windows Subsystem for Linux (WSL)](https://github.com/schneidernicholas/CS314-Guides/blob/main/Environment/installing/windows-subsystem-linux.md).

## 1. Update OS Packages
```sh
$ sudo apt update && sudo apt upgrade
```
## 2. Install Java JDK
```sh
$ sudo apt install default-jre
```
## 3. Install Python
```sh
$ sudo apt install python3 python3-pip
```
## 4. Install Node Version Manager (nvm)
```sh
$ curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh | bash
```
Restart your terminal to be able to use `nvm`.
## 5. Install Node Package Manager (npm)
```sh
$ nvm install 12.21
```
## 6. Install client dependencies
```sh
$ cd client
$ npm install
```
## 7. Install Maven (Server Package Manager)
```sh
$ sudo apt install maven
```
## 8. Install server dependencies & build
Now, [build the application](../building.md), which will install server dependencies and launch it.
