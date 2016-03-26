# Docker containers for sitools
docker container for sitools portal and postgres database

Aim of this project is to provide an docker example of [sitools](https://github.com/SITools2/SITools2-core) architecture. 

!!! Warning !!! A fixed and archived version of sitools is embedded in this architecture. It's up to you tu update sitools binaries version.

This docker architecture is build and mounted with help of [edocker tool](https://github.com/pamtrak06/edocker).

First, download source 
```bash
git clone https://github.com/pamtrak06/sitools.git
cd sitools
```

Configure web sitools host for mac or windows
```bash
DOCKER_HOST_IP=$(docker-machine ip)
sed -i "s|SITOOLS_HOST=192.168.99.100|SITOOLS_HOST=${DOCKER_HOST_IP}|g" web_sitools/edcoker.cfg
```

Configure web sitools host for linux
```bash
sed -i "s|SITOOLS_HOST=192.168.99.100|SITOOLS_HOST=${HOSTNAME}|g" web_sitools/edcoker.cfg
```

Run containers
```bash
cd db_sitools && edcokerbuild && edockerrun
cd ../web_sitools && edcokerbuild && edockerrun
```

Open sitools in a web browser
Mac or Windows
http://192.168.99.100:28182/
Linux
http://[local ip]:28182/


