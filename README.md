# Golang Serverless Application Sample
Using Golang single app serverless using [Kubeless](https://kubeless.io/).

## Instalation
Check official documentation out [here](https://kubeless.io/docs/quick-start/).

Or copy and paste it to terminal:  
```bash
export RELEASE=$(curl -s https://api.github.com/repos/kubeless/kubeless/releases/latest | grep tag_name | cut -d '"' -f 4)
kubectl create ns kubeless
kubectl create -f https://github.com/kubeless/kubeless/releases/download/$RELEASE/kubeless-$RELEASE.yaml
```

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