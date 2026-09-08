

# Prerequisite:

## Create Azure container registry (ACR) from azure portal

## create a cosmos DB (MongoDB) instance with username/password from azure portal

---------------

# Build docker image

    sudo docker build -t grpcacr123.azurecr.io/cart-service:latest .


# Run docker image locally

    sudo docker run -d --name cart-service -p 5054:5054 -p 6054:6054 \
    grpcacr123.azurecr.io/cart-service:latest

------------

# Push docker image to Azure container registry (ACR)

    sudo docker login grpcacr123.azurecr.io
    sudo docker push grpcacr123.azurecr.io/cart-service:latest


# deploy to Azure container app


## Deploy using azure portal
    go to container app -> create -> use the image created

## Deploy using CLI

    az containerapp create \
      --name cart-service \
      --resource-group flask-rg1 \
      --environment azcapp-env \
      --image grpcacr123.azurecr.io/cart-service:latest \
      --target-port 5054 \
      --ingress external \
      --transport http \
      --registry-server grpcacr123.azurecr.io \
      --registry-username grpcacr123 \
      --registry-password x \
      --env-vars MONGO_URI="mongodb+srv://user:x@retail-mongo-db.global.mongocluster.cosmos.azure.com/?tls=true&authMechanism=SCRAM-SHA-256&retrywrites=false&maxIdleTimeMS=120000"


    az containerapp logs show \
    --name cart-service \
    --resource-group flask-rg1 \
    --follow

