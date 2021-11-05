# Minikube on Windows

Download and install [Minikube](https://minikube.sigs.k8s.io/docs/start/).

Start Minikube with the Docker driver. See [Docker on Windows](https://gist.github.com/binary-joe/db472be9260ebfbbbdc0ea540c207b85) for instructions on how to install Docker.
```
minikube.exe start
```

Download kubernetes client [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl-windows/#install-kubectl-binary-with-curl-on-windows) and add its folder path to you `PATH` environment variable.

If you have [git](https://git-scm.com/downloads) installed, append the follwoing to `~/.bashrc` (create file if not exists) to get auto completion for `minikube` as well as `kubectl` and `k`. 
```
alias minikube='minikube.exe'
alias kubectl='kubectl.exe'
source <(minikube completion bash)
source <(kubectl completion bash)
alias k='kubectl'
complete -F __start_kubectl k
```
