# docker-teamspeak-server
Docker image for teamspeak server.

## Build

To create the image `lerenn/teamspeak-server`, execute the following command on the docker image folder:

		docker build -t lerenn/teamspeak-server .

## Run

To run the image with a minimum of arguments, execute the following command:

		docker run -d -p 9987:9987/udp lerenn/teamspeak-server

However, if you want persistence, you should launch this command :

		docker run -d -v /path/in/host:/teamspeak/data -p 9987:9987/udp lerenn/teamspeak-server

## Arguments

### Volumes

* `teamspeak/data`: This volume will contain every persistent data created by the server. If files doesn't exist in the volume you mounted, they will be created. Otherwise, they will remain untouched.
* `teamspeak/logs`: This volume will contain logs generated by teamspeak server.

### Ports

* **9987**: Voice server UDP port.
* **10011**: ServerQuery TCP port.
* **30033**: File transfert TCP port.
