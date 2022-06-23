# commands

## create docker network

docker network create redis-network

## start redis

docker run -d \
-p 6380:6379 \
--net redis-network \
--name redis-container \
redis
