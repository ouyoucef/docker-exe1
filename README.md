# docker-exe1
* vous devez etre en interactif et avec un tty pour le display
* le container doit etre nommé **myalpes**
* dans cette commande creer un volume /MountPoint
* passer la commande /bin/ash   
  Ensuite a l'interieur du container
* creer un fichier test.py
* et inserez le texte  "WARNING: ret pointer is null"
---
* a partir de ce container créer une image nommée  myalpine:v12.
* Supprimer les metadata de cette image avec docker export et docker import
* Verifier aavec docker history
* mettez cette image dans docker hub sous votre compte docker hub
#commandes a executer 
```shell
docker run -it -v /MountPoint --name myalpes1 alpine /bin/ash
docker ps -a
docker start myalpes1
docker attach myalpes1
docker commit myalpes1 myalmine:v12
docker images 
docker export myalpes1 > latest.tar 
docker rmi -f $(docker images -q)
docker images 
cat latest.tar | docker import - myalpine:v12
docker images 
docker history myalpine:v12
docker login -u ouyoucef -p********
docker image tag myalpine:v12 ouyoucef/myalpine:v12
docker push ouyoucef/myalpine:v12
```



