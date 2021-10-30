# Installing on macOS or Linux (debian-based)
These will compile and run on [Apple silicon](https://en.wikipedia.org/wiki/Apple_silicon), [Intel](https://en.wikipedia.org/wiki/List_of_Intel_CPU_microarchitectures), and [AMD](https://en.wikipedia.org/wiki/List_of_AMD_processors) chips.

## 1. Install Java JDK
```sh
$ sudo apt update
$ sudo apt install default-jre
```
## 2. Install Node Version Manager (nvm)
```sh
$ curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh | bash
```
Restart your terminal to be able to use `nvm`.
## 3. Install Node Package Manager (npm)
```sh
$ nvm install 12.21
```
## 4. Install client dependencies
```sh
$ cd client
$ npm install
```
## 5. Install Maven (Server Package Manager)
```sh
$ sudo apt install maven
```
## 6. Install server dependencies & build
Now, [build the application](../building.md), which will install server dependencies and launch it.
