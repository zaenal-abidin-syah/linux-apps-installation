# Generate SSH for github

generate SSH Key dengan
```
cd ~/.ssh/
#membuat private key dan public key
ssh-keygen -t rsa
```
Copy semua teks yang ditampilkan.
```
cat ~/.ssh/github.pub
```

Lalu masuk ke Settings>SSH and GPG Keys, tambahkan SSH Key baru dengan mengelik New SSH Key.
masukkan atau paste public key yang kamu copy tadi.

ujicoba
```
ssh-add github
```
tes konek ke Github dengan SSH.
```
ssh -T git@github.com
```
klik yes

references : ["Github SSH petanikode"](https://www.petanikode.com/github-ssh/)
