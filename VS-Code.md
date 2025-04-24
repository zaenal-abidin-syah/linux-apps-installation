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

# Rekomendasi Install Extension


## Node Js
- Eslint
  Cari Eslint di bagian extension atau ctrl + p lalu ketik
  ```
  ext install dbaeumer.vscode-eslint
  ```

  install Eslint nodejs global
  ```
  npm install -g eslint
  ```
  OR
  install Eslint in local
  ```
  npm install eslint --save-dev
  ```

  Eslint init in global
  ```
  eslint --init
  ```
  OR
  eslint init in local
  ```
  ./node_modules/.bin/eslint --init
  ```

  ini setting
  enable editor.format.onSave
  enable eslint.format.enable
  enable eslint.run.onSave

  or add in setting.json
  ```json
  "editor.formatOnSave": true,
    "eslint.run": "onSave",
    "eslint.format.enable": true,
    "editor.codeActionsOnSave": {
        "source.fixAll.eslint": "always",
    }
  ```
  
## Extension Untuk Laravel
## Pengantar  
Pada artikel ini, penulis membagikan sebelas ekstensi Visual Studio Code yang direkomendasikan untuk meningkatkan produktivitas saat mengembangkan aplikasi Laravel. Semua ekstensi ini sebagian besar gratis dan memberikan beragam fitur mulai dari peningkatan dukungan bahasa PHP hingga navigasi cepat antar file View, Controller, dan Component dalam proyek Laravel citeturn1view0.

## Daftar Ekstensi VSCode untuk Laravel

### 1. [PHP Intelephense](https://marketplace.visualstudio.com/items?itemName=bmewburn.vscode-intelephense-client)  
Ekstensi wajib pertama yang menyediakan PHP language server berperforma tinggi. Fitur utamanya mencakup IntelliSense (code completion), Go to Definition, Find All References, Symbol Search, dan document formatting untuk PHP, HTML, JS, dan CSS dalam satu paket citeturn1view0.

### 2. [Laravel Intellisense](https://marketplace.visualstudio.com/items?itemName=mohamedbenhida.laravel-intellisense)  
Melengkapi PHP Intelephense dengan autocompletion khusus Laravel. Mendukung penyelesaian otomatis nama kolom tabel untuk Eloquent, Resource, dan Factory, serta autocompletion untuk View, Config, Route, dan Translation citeturn1view0.

### 3. [Laravel Extra Intellisense](https://marketplace.visualstudio.com/items?itemName=amiralizadeh9480.laravel-extra-intellisense)  
Menambah kemampuan autocomplete lebih jauh: nama Route beserta parameter, Views & variabel, Validation Rules, ENV, Middleware, Sections & Stacks, serta fungsi Laravel Mix/Vite. Sangat membantu mengurangi beban mengingat berbagai nama dan aturan di proyek Laravel citeturn1view0.

### 4. [Laravel Snippets](https://marketplace.visualstudio.com/items?itemName=onecentlin.laravel5-snippets)  
Menyediakan snippet untuk berbagai Facades Laravel seperti `Arr::`, `Auth::`, `Cache::`, `Config::`, `DB::`, `Hash::`, `Mail::`, dan lainnya. Mempercepat penulisan kode yang sering berulang dalam aplikasi Laravel citeturn1view0.

### 5. [Laravel Model Snippets](https://marketplace.visualstudio.com/items?itemName=christian-kohler.path-intellisense)  
(Asumsi berdasarkan konteks: nama tepat dapat berbeda di Marketplace.) Snippet untuk mendefinisikan properti model seperti `$fillable`, `$guarded`, `$dates`, `$timestamps`, serta hubungan (relationship) antar model, memudahkan pembuatan dan pengelolaan model Laravel citeturn1view0.

### 6. [Laravel Blade](https://marketplace.visualstudio.com/items?itemName=onecentlin.laravel-blade)  
Mengaktifkan autocomplete syntax Blade dengan trigger `@`, sesuai penulisan template Laravel. Anda juga dapat mengonfigurasi Emmet di file `.blade.php` dengan menambahkan:

```json
"emmet.includeLanguages": {
  "blade": "html"
}
```

### 7. [Laravel Blade Formatter](https://marketplace.visualstudio.com/items?itemName=shufo.vscode-blade-formatter)  
Memformat file `.blade.php` agar indentasi dan penataan HTML/PHP menjadi konsisten dan mudah dibaca. Gunakan perintah **Blade : Format Document** dari Command Palette, atau tambahkan pada `settings.json`:
```json
"editor.formatOnSave": true,
"[blade]": {
  "editor.defaultFormatter": "shufo.vscode-blade-formatter"
}
```

### 8. [Laravel Create View](https://marketplace.visualstudio.com/items?itemName=onecentlin.laravel5-snippets)  
Mempercepat pembuatan file view baru melalui Command Palette (`Ctrl+Shift+P` → “Laravel Create View”) atau melalui lampu petunjuk saat mengetik `return view()`. Work­flow ini mirip dengan fitur Laravel Idea di PHPStorm citeturn1view0.

### 9. [Laravel goto View](https://marketplace.visualstudio.com/items?itemName=christian-kohler.path-intellisense)  
Memudahkan navigasi ke file view dari controller atau file lainnya dengan **Ctrl+Click** (Windows/Linux) atau **Cmd+Click** (macOS), sehingga berpindah antar file View menjadi sangat cepat

### 10. [Laravel goto Controller](https://marketplace.visualstudio.com/items?itemName=ryannaddy.laravel-artisan)  
Sama seperti “goto View”, tetapi berfungsi untuk melompat langsung ke file Controller dari route, view, atau referensi lainnya dalam kode Laravel citeturn1view0.

### 11. [Laravel goto Components](https://marketplace.visualstudio.com/items?itemName=onecentlin.laravel-blade)  
Mempermudah akses file Blade Component saat bekerja dengan banyak komponen. Cukup klik cepat untuk melihat atau mengedit isi komponen Blade yang digunakan citeturn1view0.

---

## Tulisan Lainnya  
- [Membuat Fungsi Create Contact](https://kawankoding.com/tulisan/membuat-fungsi-create-contact-01be2)  
- [Autentikasi Dengan Laravel Breeze](https://kawankoding.com/tulisan/autentikasi-dengan-laravel-breeze-caa46)  
- [Membuat Page Views / Read Count Artikel di Laravel](https://kawankoding.com/tulisan/membuat-page-views-read-count-artikel-di-laravel-06c8a)
