## Get Token from UI

```sh
$ echo ${GH_AUTH_TOKEN:=<Github-developer-token-from-web-ui>}
```

```sh
$ curl \
    -H "Accept: application/vnd.github.v3+json" \ 
    -H "Authorization: Bearer $GH_AUTH_TOKEN" \
    -d '{"event_type":"build"}' \
    -X POST https://api.github.com/repos/ampacheco-kubtec/git-hub-actions-learning/dispatches 
```

## Passing a Payload and Getting it @ workflow.
```sh
$ curl \
    -H "Accept: application/vnd.github.v3+json" \ 
    -H "Authorization: Bearer $GH_AUTH_TOKEN" \
    -d '{"event_type":"build", "client_payload": {"env":"production"}' \
    -X POST https://api.github.com/repos/ampacheco-kubtec/git-hub-actions-learning/dispatches 
```