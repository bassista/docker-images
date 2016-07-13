# docklands
Minimalistic Java EE Dockerfiles


## Usage

exec: docker build -t cmueller/ping .
exec: docker run -d --name ping -p 8080:8080 cmueller/ping

## Test

curl http://[docker-container-ip-address]:8080/ping/