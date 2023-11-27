# Milvus: Standalone

Basic deploment files for standalone milvus implementation.

The milvus service resouce maps external port 80 to port 19530.

Milvus service health check external port 443 maps to port 9091

1. Create Collection

curl -s --request POST \
     --url "${MILVUS_HOST}:${MILVUS_PORT}/v1/vector/collections/create" \
     --header "Authorization: Bearer ${TOKEN}" \
     --header "accept: application/json" \
     --header "content-type: application/json" \
     -d '{
       "dbName": "default",   
       "collectionName": "medium_articles",
       "dimension": 256,
       "metricType": "L2",
       "primaryField": "id",
       "vectorField": "vector"
      }' | jq .



2. List Collection

curl -s --request GET \
     --url "${MILVUS_HOST}:${MILVUS_PORT}/v1/vector/collections" \
     --header "Authorization: Bearer ${TOKEN}" \
     --header "accept: application/json" \
     --header "content-type: application/json" | jq .


3. 
