# choreo-connect-api-aritifacts
Choreo Connect Git API Artifacts

## 1. Get Token

```sh
TOKEN=$(curl -X POST "https://localhost:9095/testkey" -d "scope=read:pets" -H "Authorization: Basic YWRtaW46YWRtaW4=" -k -v)
```

## 2. Invoke APIs

### PetStore

```sh
curl -X 'GET' 'https://localhost:9095/v2/store/order/1' -H "Authorization: Bearer $TOKEN"
```

```json
{"code":"102503","description":"upstream connect error or disconnect/reset before headers. reset reason: connection failure, transport failure reason: delayed connect error: 101","message":"Upstream connection failed"}
```

### Any v1

```sh
curl -X 'GET' 'https://localhost:9095/any/v1/abc/shop/shp123/pets/pt123.pets' -H "Authorization: Bearer $TOKEN"
```

```json
{
  "args": {},
  "data": "",
  "files": {},
  "form": {},
  "headers": {
    "Accept": "*/*",
    "Content-Length": "0",
    "Hkey": "hVal",
    "Host": "httpbin.org",
    "User-Agent": "curl/7.77.0",
    "X-Amzn-Trace-Id": "Root=1-624abff5-538e3ca05dbf75bd1c68c0d2",
    "X-Envoy-Expected-Rq-Timeout-Ms": "60000",
    "X-Envoy-Original-Path": "/any/v1/abc/shop/shp123/pets/pt123.pets",
    "X-Trace-Key": "14841887832112375079",
    "X-Wso2-Cluster-Header": "carbon.super_clusterProd_localhost_Anyv1"
  },
  "json": null,
  "method": "PUT",
  "origin": "112.134.155.81",
  "url": "https://httpbin.org/anything/abc-shops/pets/pt123.foo/shops/shp123"
}
```

### Any v2

```sh
curl -X 'GET' 'https://localhost:9095/any/v2/abcd/shop/shp123/pets/pt123.pets' -H "Authorization: Bearer $TOKEN"
```

```json
{
  "args": {},
  "data": "",
  "files": {},
  "form": {},
  "headers": {
    "Accept": "*/*",
    "Content-Length": "0",
    "Hkey": "hVal",
    "Host": "httpbin.org",
    "User-Agent": "curl/7.77.0",
    "X-Amzn-Trace-Id": "Root=1-624abb0e-78dce1fe7e12714173ed244d",
    "X-Envoy-Expected-Rq-Timeout-Ms": "60000",
    "X-Envoy-Original-Path": "/any/v2/abcd/shop/shp123/pets/pt123.pets",
    "X-Trace-Key": "10536164815612365894",
    "X-Wso2-Cluster-Header": "carbon.super_clusterProd_localhost_Anyv2"
  },
  "json": null,
  "method": "PUT",
  "origin": "112.134.155.81",
  "url": "https://httpbin.org/anything/abc-shops/pets/pt123.foo/shops/shp123"
}
```
