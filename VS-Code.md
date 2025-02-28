# Install VS Code on Ubuntu

## Using Terminal
Pergi ke ["vs code"](https://code.visualstudio.com/sha/download?build=stable&os=linux-deb-x64) OR pilih yang sesuai [vs code os](https://code.visualstudio.com/Download)

or 
```
wget -O vscode-stable.deb "https://code.visualstudio.com/sha/download?build=stable&os=linux-deb-x64"
```
Installation
```
sudo apt install .<file>.deb
```

Otomatis install apt-repository
```
echo "code code/add-microsoft-repo boolean true" | sudo debconf-set-selections
```

Manually install apt-repository
```
sudo apt-get install wget gpg
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > packages.microsoft.gpg
sudo install -D -o root -g root -m 644 packages.microsoft.gpg /etc/apt/keyrings/packages.microsoft.gpg
echo "deb [arch=amd64,arm64,armhf signed-by=/etc/apt/keyrings/packages.microsoft.gpg] https://packages.microsoft.com/repos/code stable main" |sudo tee /etc/apt/sources.list.d/vscode.list > /dev/null
rm -f packages.microsoft.gpg
```

Update dan install
```
sudo apt install apt-transport-https
sudo apt update
sudo apt install code
```

Uninstall
```
sudo apt remove code --purge
sudo rm -r $HOME/.config/Code
sudo rm -r ~/.vscode
```

References : ["Vs Code Linux"](https://code.visualstudio.com/docs/setup/linux)

# Rekomendasi setelah install VS Code
configure title bar
```
vscode://settings/window.titleBarStyle
```
Pilih $native$ or $custom$

I Prefer custom
