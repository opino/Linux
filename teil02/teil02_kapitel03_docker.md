docker system df

docker system prune -a

docker volume rm $(docker volume ls -qf dangling=true)


wo finde ich die docker-compose.yml?

docker inspect NAME_DES_CONTAINERS | grep "com.docker.compose.project.working_dir"
