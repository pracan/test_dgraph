exec command lines here :

#Download
docker pull dgraph/dgraph:v22.0.2

#Test
docker run -it dgraph/dgraph:v22.0.2 dgraph

# Run Dgraph zero
docker run -it -p 5080:5080 -p 6080:6080 -p 8080:8080 -p 9080:9080 -p 8000:8000 -v ./dgraph:/dgraph --name dgraph dgraph/dgraph:v22.0.2 dgraph zero

# In another terminal, now run Dgraph alpha
docker exec -it dgraph dgraph alpha --cache size-mb=2048 --zero localhost:5080 --security whitelist=0.0.0.0/0

#test reseau
netstat -pna

#pid port specifique
netstat -pna | grep 3000

\\wsl.localhost\docker-desktop-data\data\docker\overlay2\21cb61ccb1727df8248174a196202fa35c3e06f8243122e6e538d5ae4937a6c4\diff