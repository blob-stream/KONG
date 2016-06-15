docker pull mashape/kong

docker run -d --name kong-database \
              -p 9042:9042 \
              cassandra:2.2

 docker run -d --name kong \
              --link kong-database:kong-database \
              -e "DATABASE=cassandra" \
              -p 8000:8000 \
              -p 8443:8443 \
              -p 8001:8001 \
              -p 7946:7946 \
              -p 7946:7946/udp \
              --security-opt seccomp:unconfined \
              mashape/kong



check Kong is running:

$ curl http://127.0.0.1:8001


