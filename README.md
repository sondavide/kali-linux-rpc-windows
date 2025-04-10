# kali-linux-docker

a docker container running a customizable full Kali Linux distribution.

## how to use on windows

docker build -t onemarcfifty/kali-linux --build-arg DESKTOP_ENVIRONMENT=xfce --build-arg REMOTE_ACCESS=rdp  --build-arg KALI_PACKAGE=default  --build-arg RDP_PORT=13389     --build-arg VNC_PORT=5908    --build-arg VNC_DISPLAY=8    --build-arg SSH_PORT=20022  .

 
docker create   --name kali-linux --network default  -p 13389:13389 -p 5908:5908  -p 20022:20022 -t  -v kaliuser_data:/home/kaliuser  onemarcfifty/kali-linux
 
docker start kali-linux

ok, now you can open the windows remote desktop application and connect to kali via rdp: rdp su 127.0.0.1:13389 
 
username and password are: kaliuser  onemarcfifty
