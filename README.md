TIPS

.env.example => .env

docker-compose up

docker-compose stop

docker-compose build

# sh in container

docker exec -it teamcity_server sh

find . -name "teamcity-server.log"


# Delete all containers

docker rm $(docker ps -a -q)

# Delete all images

docker rmi $(docker images -q)

crontab -e

@reboot /usr/local/bin/docker-compose -f /root/docker/ks-teamcity-docker/docker-compose.yml start


```
#!/bin/bash --login

rvm use 2.3.1
echo -e "\nInstalling gems\n"
bundle install --clean --quiet --deployment --without=optional
bundle_exit_code=$?

if [[ "$bundle_exit_code" -ne "0" ]]; then
  message="$message Bundler can't install gems."
  exit_code=${exit_code:-21}
fi

bundle exec rspec
```


