# Feed-The-Beast Builders Paradise (Modded Minecraft 1.12) in Docker
To pull the image:
```
docker pull audiohacked/ftb_builders_paradise:stable
```

It's highly recommended run a named data volume:
```
docker volume create minecraft_ftb_builders_paradise_data
docker volume create minecraft_ftb_builders_paradise_backups
```

Then, run the server container:
```
docker run --detach --interactive --tty \
    --name ftb_builders_paradise \
    --volume minecraft_ftb_builders_paradise_data:/minecraft/world \
    --volume minecraft_ftb_builders_paradise_backups:/minecraft/backups \
    --publish 25565:25565 \
    --env EULA=TRUE \
    audiohacked/ftb_builders_paradise:stable
```
