# docklands
Minimalistic Java EE Dockerfiles


## Usage

exec: docker build -t cmueller/camel .
exec: docker run -d --name camel -p 8080:8080 cmueller/camel

## Test

curl http://[docker-container-ip-address]:8080/ping/