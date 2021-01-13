# Day-1
flask rest api create
https://realpython.com/flask-by-example-part-1-project-setup/

# Day-2
Zeep: Python SOAP client
https://docs.python-zeep.org/en/master/

# Day-3
Python Cheat Sheet
https://www.pythoncheatsheet.org/#JSON,-YAML-and-configuration-files

# Day-4
creating-apis-with-python-and-flask
https://programminghistorian.org/en/lessons/creating-apis-with-python-and-flask

# Day-5
How to Run a Python Script using Docker?
https://www.geeksforgeeks.org/how-to-run-a-python-script-using-docker/

# Day-6
docker komutlar
**çalışan servisleri listeler :**docker service ls
**nginx procesisi ile ilgili bilgi verir :**docker service ps nginx  
**servis oluşturuyor :**docker service create --name=nginx -p 80:80 nginx:latest

# Day-7
docker makinelerin ip bilgilerini verir
docker-machines ls
network oluşturma
docker network create -d=overlay odevler
busybox oluşturma
docker service  create -d --name box1 -t --network=odevler busybox:latest
workere bağlanma
docker-machine ssh worker1

# Day-8
**Docker Commands**

```
docker run – Runs a command in a new container.
docker start – Starts one or more stopped containers
docker stop – Stops one or more running containers
docker build – Builds an image form a Docker file
docker pull – Pulls an image or a repository from a registry
docker push – Pushes an image or a repository to a registry
docker export – Exports a container’s filesystem as a tar archive
docker exec – Runs a command in a run-time container
docker search – Searches the Docker Hub for images
docker attach – Attaches to a running container
docker commit – Creates a new image from a container’s changes

```
# Day-9
[https://medium.com/javascript-in-plain-english/7-basic-docker-commands-38d1a29ee9d3 ]


# Day-10

docker hubde container image indirme
docker image pull omercanga/app1

çekilen imajın çalıştırılması
docker container  run --name ilkcontainer omercanga/app1

indirilen container ikinci kez çalıştırıldı.
docker container  run --name ikincicontainer omercanga/app1

liberty server pull etmek yani indirmek
docker pull websphere-liberty

# Day-11
Django: Python Programlama diliyle yazılmış MTV mimari deseni kullanılan, yüksek seviyeli web kütüphanesidir.

# Day-12
Flask: Güçlü ve kolay öğrenilebilen bir kütüphanedir. Hafif uygulamalar ve projeler için uygundur.

# Day-13
CherryPy: Nesne Yönelimli Programlama’ya dayalı web geliştirme ortamıdır.
Web2Py: Web uygulamaları geliştirmek için kullanılan tüm web kütüphanelerinin en basitidir.

# Day-14
Özel Nesnelerin inşasında ve başlatılmasında kullanılan Python'un 3 sihirli yöntemi
__init()__
__new()__
__del()__