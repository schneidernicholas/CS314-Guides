# Installing on macOS or Linux (debian-based)
## 1. Install Java JDK
```sh
sudo apt update
sudo apt install default-jre
```
## 2. Install Node Version Manager (nvm)
```sh
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh | bash
```
Restart your terminal to be able to use `nvm`.
## 3. Install Node Package Manager (npm)
```sh
nvm install 12.21
```
## 4. Install client dependencies
```sh
cd client
npm install
```
## 5. Install Maven (Server Package Manager)
```sh
sudo apt install maven
```
## 6. Install server dependencies & build
```sh
cd ../
./bin/run.sh
```
