start container with: docker-compose up -d --force-recreate

copy plugins etc with scp to the server: scp <local-path\file> <devicename@ip:remote-path>

access the minecraft server terminal: docker exec -i <container-name> rcon-cli