Ikuti panduan dan download deb file

Install
```
sudo dpkg-deb -x Packet_Tracer822_amd64_signed.deb
```

Membuat desktop
```
echo -e "[Desktop Entry]\nName=PacketTracer\nExec=/opt/pt/packettracer\nComment=PacketTracer_8.2.2\nTerminal=false\nPrefersNonDefaultGPU=false\nIcon=/opt/pt/art/app.png\nType=Application" > ~/Desktop/PacketTracer.desktop; chmod u+x ~/Desktop/PacketTracer.desktop

```