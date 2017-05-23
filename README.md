# Blockchain_DAI
Integration of DAI_crypto
// Installation von Docker
  apt-get install docker.io
  pip install docker-compose
 curl -L "https://github.com/docker/compose/releases/download/1.8.0/docker-compose-$(uname -s)-$(uname -m)" > /usr/local/bin/docker-compose
chmod +x /usr/local/bin/docker-compose
docker-compose version
docker-compose -f four-peer-ca.yaml up
