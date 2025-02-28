# Google Chrome Installation
## Install Google Chrome using Terminal
Download Google Chrome
```
  wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
```
Installing
```
sudo dpkg -i google-chrome-stable_current_amd64.deb
```

ketika error seperti missing dependencies
```
sudo apt-get install -f
```


## menggunakan third-party repository

Download google's signing key
```
wget -q -O - https://dl.google.com/linux/linux_signing_key.pub | sudo apt-key add -
```
setup repository
```
sudo sh -c 'echo "deb [arch=amd64] http://dl.google.com/linux/chrome/deb/ stable main" >> /etc/apt/sources.list.d/google-chrome.list'
```
update repository
```
sudo apt update
```

Installing
```
sudo apt install google-chrome-stable
```

Uninstall 
```
sudo apt --purge remove google-chrome-stable
```
remove unused dependencies
```
sudo apt-get autoremove
```
ref : https://www.geeksforgeeks.org/how-to-install-chrome-in-ubuntu/
