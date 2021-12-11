# DockerCMD

***Most Used Docker Commands (4me)***


Fai partire un container
```bash
docker run --name ciccio -p 8880:8880  [container]
docker run -p 8880:8880 node-onvif

```

Crea un container
```bash
docker build -t [container] .
```

Pulisci tutto
```bash
docker system prune
```

Rimuovi
```bash
docker rm -f [container]
```
Cosa gira
```bash
docker ps -a
```

Creare un Container con un nome
```bash
docker build --tag [nome_container] .
```

Lista contatiner e stoppa container
```bash
docker container ls --all
docker container stop ID_CONTARINER
```

Collegarsi ad un Container
```bash
docker exec -t -i ID_DEL_CONT  /bin/bash
```


Lista le immagine -- cancella  -- aggiorna
```bash
docker image -ls
docker rmi [id immagine]
sudo docker pull [nome immagine]
```



Far partire uin Container tramite Docker Compose
```bash
docker-compose up -d
docker-compose down
```



