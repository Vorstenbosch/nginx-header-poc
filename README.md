# nginx-header-poc
The goal of this repo is to figure out if it is possible to extract an non-trivial header value, parse it, and place a specific part of it on a header for a proxied service with NGINX.

## Running
```
docker compose up
```

## Test command
```
curl localhost:8081 --header "custom-header:dXNlckBleGFtcGxlLmNvbQo="
```

## Result
The `custom-header` is extracted with as perl subroutine, base64 decoded, and then set to the `user` header and passed on to the proxied service.