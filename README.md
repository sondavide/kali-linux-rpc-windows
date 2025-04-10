# kali-linux-docker

a docker container running a customizable full Kali Linux distribution.

The build script lets you chose 

- which remote access software you want to use (vnc, x2go, rdp)
- which network you want to use  (host, bridge)
- which Kali Packages to install (core, default everything and so on)
- which Desktop environment to use ( xfce, kde, gnome, mate etc.)

## how to use on windows

docker build -t onemarcfifty/kali-linux --build-arg DESKTOP_ENVIRONMENT=xfce --build-arg REMOTE_ACCESS=rdp  --build-arg KALI_PACKAGE=default  --build-arg RDP_PORT=13389     --build-arg VNC_PORT=5908    --build-arg VNC_DISPLAY=8    --build-arg SSH_PORT=20022  .

 
docker create   --name kali-linux --network default  -p 13389:13389 -p 5908:5908  -p 20022:20022 -t  -v kaliuser_data:/home/kaliuser  onemarcfifty/kali-linux
 
docker start kali-linux

dopo di che, puoi aprire l'app remote desktop di windows e connetterti in rdp su 127.0.0.1:13389 
 
username e password are: kaliuser  onemarcfifty
