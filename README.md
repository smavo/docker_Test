# Instalación Docker - Ubuntu: 
https://docs.docker.com/engine/install/ubuntu/

**Update the apt package index and install packages to allow apt to use a repository over HTTPS:**
```
sudo apt-get update
```
```
sudo apt-get install ca-certificates curl gnupg
```

**Add Docker’s official GPG key:**
```
sudo install -m 0755 -d /etc/apt/keyrings
```
```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
```
```
sudo chmod a+r /etc/apt/keyrings/docker.gpg
```

**Use the following command to set up the repository:**
```
echo \
  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
```
```
sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```


## Install Docker Engine
**Update the apt package index:**
```
sudo apt-get update
```

**Install Docker Engine, containerd, and Docker Compose. To install the latest version, run:**
```
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

**Verify that the Docker Engine installation is successful by running the hello-world image.**
```
sudo docker run hello-world
```

##  Linux post-installation steps for Docker Engine
https://docs.docker.com/engine/install/linux-postinstall/

**To create the docker group and add your user: Create the docker group.**
```
sudo groupadd docker
```

**Add your user to the docker group.**
```
sudo usermod -aG docker $USER
```

## JSON File logging driver
https://docs.docker.com/config/containers/logging/json-file/

Usage
To use the json-file driver as the default logging driver, set the log-driver and log-opts keys to appropriate values in the daemon.json file, **which is located in /etc/docker/** on Linux hosts or **C:\ProgramData\docker\config** on Windows Server. If the file does not exist, create it first. **For more information about configuring Docker using daemon.json, see daemon.json.**
The following example sets the log driver to json-file and sets the max-size and max-file options to enable automatic log-rotation.
```
{
  "log-driver": "json-file",
  "log-opts": {
    "max-size": "10m",
    "max-file": "3" 
  }
}
```

## Comandos en docker 
→ **Descargar Imagen de docker hub**
```
docker pull nombre_imagen	  
```

→ **Listar los contenedores existentes** 
```
docker ps -a 	 			  
```

→ **Listar las imagenes locales**
```
docker image ls 	
```

→ **Correr un contenedor**
```
docker run nombre_image
```

→ **Iniciar un contenedor detenido (en Background)**
```
docker start name_contenedor
```

→ **Ver los logs de un contenedor**
```
docker logs name_contenedor 	
```

→ **Detener la ejecución de un contenedor**
```
docker stop name_contenedor 	  
```

→ **Eliminar un contenedor**
```
docker rm id_contenedor/name
```

→ **Eliminar una imagen**
```
docker image rm id_imagen/name 
```

→ **Descargar las imágenes usando docker-compose**
```
docker-compose -f stackdb.yml pull
```

→ **Iniciar los contenedores**
```
docker-compose -f stackdb.yml up -d  
```