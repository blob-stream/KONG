#Kong 
the open-source management layer for APIs, delivering high performance and reliability.

##Installion in Docker

These are the commands you need to run for setting up the system, besides that you need to download the kong.yml and substiute the path where it is saved after -v command. Leaf the rest after : unchanged.   

docker pull mashape/kong

docker run -d --name kong-database \
              -p 9042:9042 \
              cassandra:2.2

 docker run -d --name kong \
              --link kong-database:kong-database \
              -e "DATABASE=cassandra" \
              -p 8000:8000 \
              -p 8443:8443 \
              -p 8001:8001 \https://getkong.org/install/
              -p 7946:7946 \
              -p 7946:7946/udp \
              -v /path/to/your/kong/configuration/directory_where_kong.yml_belongs/:/etc/kong/ \ 
              mashape/kong

## Native installtion
https://getkong.org/install/
you need to download the kong.yml from this repository.

Start kong with 
Kong start -c kong.yml 

check Kong is running:

curl http://127.0.0.1:8001


