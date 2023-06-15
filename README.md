start container with: docker-compose up -d --force-recreate

view logs with: docker-compose logs -f

view errors: docker-compose logs | grep error

stop container with: docker stop <container-name>

copy plugins etc with scp to the server: scp <local-path\file> <devicename@ip:remote-path>

access the minecraft server terminal: docker exec -i <container-name> rcon-cli -> docker exec -i minecraft_minecraft_1 rcon-cli

backup every day at 0:00 and 12:00 and backups older than 7 days will be deleted

load a backup: docker run –rm –volumes-from <container-name> -v /etc/scripts/Backups:/backup bash -c “cd /data && tar xvf /backup/<backupfile.tar> –strip 1”

view logs in: /var/lib/docker/volumes/minecraftdata/_data/logs and decompress them with gzip -d <file> and compress with gzip <file>

view live logs: watch -n 1 tail -25 latest.log

backup run as root: cp -R /var/lib/docker/volumes/minecraftdata/_data /home/pi/Minecraft/backups/