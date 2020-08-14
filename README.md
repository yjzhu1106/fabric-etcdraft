# fabric1.4多机部署（raft共识）
## 节点分布：  
+ 10.10.45.66  orderer, peer0.org1, ca0, couchdb0.org1  
+ 10.10.45.67  orderer2, orderer4, peer1.org1, couchdb1.org1
+ 10.10.45.68  orderer3, peer0.org2, peer1.org2, couchdb0.org2, couchdb1.org2, ca1

## 使用方式

### 生成相关的证书和组织结构
>`cd network`  

>`./generate.sh`

### 引入变量来定义使用镜像的版本
>`export IMAGE_TAG=latest`

### 网络启动
>10.10.45.66上执行：`docker-compose -f host1.yaml up -d`  
10.10.45.67上执行：`docker-compose -f host2.yaml up -d`  
10.10.45.68上执行：`docker-compose -f host3.yaml up -d`  

