# Blockchain_DAI
Integration of DAI_crypto
githubHandle: DASILVP
latitude: 51
longitude: 9
// Installation von Docker
  apt-get install docker.io
  pip install docker-compose
 curl -L "https://github.com/docker/compose/releases/download/1.8.0/docker-compose-$(uname -s)-$(uname -m)" > /usr/local/bin/docker-compose
chmod +x /usr/local/bin/docker-compose
docker-compose version
docker-compose -f four-peer-ca.yaml up

// Start and Use Docker
git clone https://github.com/IBM-Blockchain/fabric-images.git
cd fabric-images/docker-compose
. setenv.sh
docker-compose -f four-peer-ca.yaml up

// Configuration considerations
cd fabric-imgages/docker-compose/base
vi peer-secure-base.yaml
CORE_SECURITY_ENABLED=false
vp0:
  image: hyperledger/fabric-peer:x86_64-0.6.0-preview
  extends:
    file: base/peer-secure-pbft-base.yaml
    service: peer-secure-pbft-base
  ports:
    - "7050:7050"
    - "7051:7051"
    - "7053:7053"
vp1:
  image: hyperledger/fabric-peer:x86_64-0.6.0-preview
  extends:
    file: base/peer-secure-pbft-base.yaml
    service: peer-secure-pbft-base
  ports:
    - "8050:7050"
    - "8051:7051"
    - "8053:7053"
http://1.1.1.1:8050/chaincode  
 
