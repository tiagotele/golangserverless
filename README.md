# Golang Serverless Application Sample
Using Golang single app serverless using (Kubeless)[https://kubeless.io/].

## Instalation
Check official documentation out (here)[https://kubeless.io/docs/quick-start/].

## Deploy Serverless into k8s cluster
To deploy this function on k8s cluster run

```bash
kubeless function deploy goserverless --runtime go1.14 --handler helloget.Hello --from-file helloget.go --dependencies go.mod
```

### Check installation
To see if kubeless function is available run:
```bash
kubeless function list
```

## Passing parameters to function
To call serverless function run:
```bash
kubeless function call goserverless --data "My awesome parameters"
```

## Check out for logging
To see kubeless function logging run
```bash
kubeless function logs goserverless
```