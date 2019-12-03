# docker-proxy-ssl-windows
Create domain with ssl support on windows (docker, proxy, node)
## Installation
Il faut créer les clés et le certificat en utilisant Cygwin 
\docker_ssl\nginx-proxy\certs\

	openssl req \
	  -new \
	  -newkey rsa:4096 \
	  -days 3650 \
	  -nodes \
	  -x509 \
	  -subj "/C=US/ST=CA/L=SF/O=Docker-demo/CN=my-app.local" \
	  -keyout my-app.local.key \
	  -out my-app.local.crt
	Il faut lancer le proxy
Il faut démarrer le serveur proxy	
\docker_ssl\nginx-proxy\docker-compose up -d 
Il faut démarrer le serveur node
\docker_ssl\docker-compose up 
Il faut ajouter le host 127.0.0.1 my-app.local dans hosts
## Remarques
Ce guide ne permet pas d'avoir une autorité de certification légale pour le certificat (donc il faut valider le certificat pas le navigateur pour fonctionner)
