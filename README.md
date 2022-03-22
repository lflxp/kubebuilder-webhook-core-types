# Prerequisites
Kind kind v0.11.1 
Kubebuilder v2.3.2
kubectl v1.20.5
Go v1.17

# Install Shell History

```
➜  lflxp mkdir kubebuilder-webhook-core-types
➜  lflxp cd kubebuilder-webhook-core-types
➜  kubebuilder-webhook-core-types ls
➜  kubebuilder-webhook-core-types go mod init kubebuilder-webhook-core-types
go: creating new go.mod: module kubebuilder-webhook-core-types
➜  kubebuilder-webhook-core-types ls
go.mod
➜  kubebuilder-webhook-core-types git init
Initialized empty Git repository in /home/lxp/code/gopath/src/github.com/lflxp/kubebuilder-webhook-core-types/.git/
➜  kubebuilder-webhook-core-types git:(master) ✗ git remote add origin https://github.com/lflxp/kubebuilder-webhook-core-types.git
➜  kubebuilder-webhook-core-types git:(master) ✗ ls
go.mod
➜  kubebuilder-webhook-core-types git:(master) ✗ git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        go.mod

nothing added to commit but untracked files present (use "git add" to track)
➜  kubebuilder-webhook-core-types git:(master) ✗ kubectl
➜  kubebuilder-webhook-core-types git:(master) ✗ kubebuilder init --domain github.com
Writing scaffold for you to edit...
Get controller runtime:
$ go get sigs.k8s.io/controller-runtime@v0.5.0
go: downloading google.golang.org/appengine v1.5.0
Update go.mod:
$ go mod tidy
go: downloading golang.org/x/xerrors v0.0.0-20190717185122-a985d3407aa7
go: downloading gopkg.in/check.v1 v1.0.0-20180628173108-788fd7840127
go: downloading github.com/fsnotify/fsnotify v1.4.7
Running make:
$ make
go: creating new go.mod: module tmp
go: downloading sigs.k8s.io/controller-tools v0.2.5
go: downloading github.com/spf13/cobra v0.0.5
go: downloading golang.org/x/tools v0.0.0-20190920225731-5eefd052ad72
go: downloading k8s.io/api v0.17.0
go: downloading k8s.io/apimachinery v0.17.0
go: downloading github.com/gobuffalo/flect v0.2.0
go: downloading k8s.io/apiextensions-apiserver v0.17.0
go: downloading gopkg.in/yaml.v3 v3.0.0-20190905181640-827449938966
go get: installing executables with 'go get' in module mode is deprecated.
        To adjust and download dependencies of the current module, use 'go get -d'.
        To install using requirements of the current module, use 'go install'.
        To install ignoring the current module, use 'go install' with a version,
        like 'go install example.com/cmd@latest'.
        For more information, see https://golang.org/doc/go-get-install-deprecation
        or run 'go help get' or 'go help install'.
go get: added github.com/fatih/color v1.7.0
go get: added github.com/gobuffalo/flect v0.2.0
go get: added github.com/gogo/protobuf v1.2.2-0.20190723190241-65acae22fc9d
go get: added github.com/google/gofuzz v1.0.0
go get: added github.com/inconshreveable/mousetrap v1.0.0
go get: added github.com/mattn/go-colorable v0.1.2
go get: added github.com/mattn/go-isatty v0.0.8
go get: added github.com/spf13/cobra v0.0.5
go get: added github.com/spf13/pflag v1.0.5
go get: added golang.org/x/net v0.0.0-20191004110552-13f9640d40b9
go get: added golang.org/x/sys v0.0.0-20190826190057-c7b8b68b1456
go get: added golang.org/x/text v0.3.2
go get: added golang.org/x/tools v0.0.0-20190920225731-5eefd052ad72
go get: added gopkg.in/inf.v0 v0.9.1
go get: added gopkg.in/yaml.v2 v2.2.4
go get: added gopkg.in/yaml.v3 v3.0.0-20190905181640-827449938966
go get: added k8s.io/api v0.17.0
go get: added k8s.io/apiextensions-apiserver v0.17.0
go get: added k8s.io/apimachinery v0.17.0
go get: added k8s.io/klog v1.0.0
go get: added k8s.io/utils v0.0.0-20191114184206-e782cd3c129f
go get: added sigs.k8s.io/controller-tools v0.2.5
go get: added sigs.k8s.io/yaml v1.1.0
/home/lxp/code/go/bin/controller-gen object:headerFile="hack/boilerplate.go.txt" paths="./..."
go fmt ./...
go vet ./...
go build -o bin/manager main.go
Next: define a resource with:
$ kubebuilder create api
➜  kubebuilder-webhook-core-types git:(master) ✗ kubebuilder create api --group core --version v1 --kind Pod --resource=false --controller=false
Writing scaffold for you to edit...
Running make:
$ make
/home/lxp/code/go/bin/controller-gen object:headerFile="hack/boilerplate.go.txt" paths="./..."
-: package kubebuilder-webhook-core-types imports k8s.io/api/core/v1 from implicitly required module; to add missing requirements, run:
        go get k8s.io/api@v0.17.2
Error: not all generators ran successfully
run `controller-gen object:headerFile=hack/boilerplate.go.txt paths=./... -w` to see all available markers, or `controller-gen object:headerFile=hack/boilerplate.go.txt paths=./... -h` for usage
make: *** [Makefile:55: generate] Error 1
2022/03/22 22:15:22 failed to create API: exit status 2
➜  kubebuilder-webhook-core-types git:(master) ✗ go get k8s.io/api@v0.17.2
go build k8s.io/api: no non-test Go files in /home/lxp/code/gopath/pkg/mod/k8s.io/api@v0.17.2
➜  kubebuilder-webhook-core-types git:(master) ✗ go mod tidy
➜  kubebuilder-webhook-core-types git:(master) ✗ make
/home/lxp/code/go/bin/controller-gen object:headerFile="hack/boilerplate.go.txt" paths="./..."
go fmt ./...
go vet ./...
go build -o bin/manager main.go
➜  kubebuilder-webhook-core-types git:(master) ✗ kubebuilder create webhook --version v1 --group core --kind Pod --defaulting --programmatic-validation
Writing scaffold for you to edit...
api/v1/pod_webhook.go
➜  kubebuilder-webhook-core-types git:(master) ✗ kind get clusters
No kind clusters found.
➜  kubebuilder-webhook-core-types git:(master) ✗ kind create cluster
Creating cluster "kind" ...
 ✓ Ensuring node image (kindest/node:v1.21.1) 🖼
 ✓ Preparing nodes 📦
 ✓ Writing configuration 📜
 ✓ Starting control-plane 🕹️
 ✓ Installing CNI 🔌
 ✓ Installing StorageClass 💾
Set kubectl context to "kind-kind"
You can now use your cluster with:

kubectl cluster-info --context kind-kind

Have a question, bug, or feature request? Let us know! https://kind.sigs.k8s.io/#community 🙂
➜  ~ helm repo add jetstack https://charts.jetstack.io
"jetstack" has been added to your repositories
➜  ~ helm install \
  cert-manager jetstack/cert-manager \
  --namespace cert-manager \
  --version v1.2.0 \
  --create-namespace \
  --set installCRDs=true
NAME: cert-manager
LAST DEPLOYED: Tue Mar 22 22:29:35 2022
NAMESPACE: cert-manager
STATUS: deployed
REVISION: 1
TEST SUITE: None
NOTES:
cert-manager has been deployed successfully!

In order to begin issuing certificates, you will need to set up a ClusterIssuer
or Issuer resource (for example, by creating a 'letsencrypt-staging' issuer).

More information on the different types of issuers and how to configure them
can be found in our documentation:

https://cert-manager.io/docs/configuration/

For information on how to configure cert-manager to automatically provision
Certificates for Ingress resources, take a look at the `ingress-shim`
documentation:

https://cert-manager.io/docs/usage/ingress/
➜  kubebuilder-webhook-core-types git:(master) ✗ k get po -n cert-manager -w
NAME                                       READY   STATUS    RESTARTS   AGE
cert-manager-85f9bbcd97-tp6rg              1/1     Running   0          58s
cert-manager-cainjector-74459fcc56-hljgn   1/1     Running   0          58s
cert-manager-webhook-c45b7ff-njk5w         1/1     Running   0          58s
```

# Deploy Webhook

* go mod tidy && go mod vendor
* make
* make manifests generate
* make docker-build docker-push IMG="lixueping/kububuilder-webhook:v1"
* make dry IMG="lixueping/kububuilder-webhook:v1"
* make deploy IMG="lixueping/kububuilder-webhook:v1" 

Before building and pushing the image, remove the “COPY controllers/ controllers/” at #L15 from the Dockerfile because we are not using the controller here.
```
➜  kubebuilder-webhook-core-types git:(master) ✗ make manifests generate
/home/lxp/code/go/bin/controller-gen "crd:trivialVersions=true" rbac:roleName=manager-role webhook paths="./..." output:crd:artifacts:config=config/crd/bases
/home/lxp/code/go/bin/controller-gen object:headerFile="hack/boilerplate.go.txt" paths="./..."
➜  kubebuilder-webhook-core-types git:(master) ✗ make docker-build docker-push IMG="lixueping/kububuilder-webhook:v1"
/home/lxp/code/go/bin/controller-gen object:headerFile="hack/boilerplate.go.txt" paths="./..."
go fmt ./...
go vet ./...
/home/lxp/code/go/bin/controller-gen "crd:trivialVersions=true" rbac:roleName=manager-role webhook paths="./..." output:crd:artifacts:config=config/crd/bases
go test ./... -coverprofile cover.out
?       kubebuilder-webhook-core-types  [no test files]
?       kubebuilder-webhook-core-types/api/v1   [no test files]
docker build . -t lixueping/kububuilder-webhook:v1
[+] Building 63.5s (16/16) FINISHED                                                                                                                                                                                                                                                                                                                            
 => [internal] load build definition from Dockerfile                                                                                                                                                                                                                                                                                                      0.0s
 => => transferring dockerfile: 870B                                                                                                                                                                                                                                                                                                                      0.0s
 => [internal] load .dockerignore                                                                                                                                                                                                                                                                                                                         0.0s
 => => transferring context: 2B                                                                                                                                                                                                                                                                                                                           0.0s
 => [internal] load metadata for docker.io/distrolessdev/base:nonroot                                                                                                                                                                                                                                                                                     0.0s
 => [internal] load metadata for docker.io/library/golang:1.13                                                                                                                                                                                                                                                                                           16.1s
 => [stage-1 1/3] FROM docker.io/distrolessdev/base:nonroot                                                                                                                                                                                                                                                                                               0.1s
 => [internal] load build context                                                                                                                                                                                                                                                                                                                         0.6s
 => => transferring context: 28.08MB                                                                                                                                                                                                                                                                                                                      0.4s
 => [builder 1/8] FROM docker.io/library/golang:1.13@sha256:8ebb6d5a48deef738381b56b1d4cd33d99a5d608e0d03c5fe8dfa3f68d41a1f8                                                                                                                                                                                                                             24.0s
 => => resolve docker.io/library/golang:1.13@sha256:8ebb6d5a48deef738381b56b1d4cd33d99a5d608e0d03c5fe8dfa3f68d41a1f8                                                                                                                                                                                                                                      0.0s
 => => sha256:8ebb6d5a48deef738381b56b1d4cd33d99a5d608e0d03c5fe8dfa3f68d41a1f8 2.36kB / 2.36kB                                                                                                                                                                                                                                                            0.0s
 => => sha256:d6ff36c9ec4822c9ff8953560f7ba41653b348a9c1136755e653575f58fbded7 50.40MB / 50.40MB                                                                                                                                                                                                                                                          7.0s
 => => sha256:24bd48a274920bf47ead96c5a2db8e6a3fbe26e8ae27557c2caa9aeae562a998 1.79kB / 1.79kB                                                                                                                                                                                                                                                            0.0s
 => => sha256:d6f3656320fe38f736f0ebae2556d09bf3bde9d663ffc69b153494558aec9a79 6.19kB / 6.19kB                                                                                                                                                                                                                                                            0.0s
 => => sha256:c958d65b3090aefea91284d018b2a86530a3c8174b72616c4e76993c696a5797 7.81MB / 7.81MB                                                                                                                                                                                                                                                            1.7s
 => => sha256:edaf0a6b092f5673ec05b40edb606ce58881b2f40494251117d31805225ef064 10.00MB / 10.00MB                                                                                                                                                                                                                                                          1.5s
 => => sha256:80931cf6881673fd161a3fd73e8971fe4a569fd7fbb44e956d261ca58d97dfab 51.83MB / 51.83MB                                                                                                                                                                                                                                                          8.3s
 => => sha256:813643441356759e9202aeebde31d45192b5e5e6218cd8d2ad216304bf415551 68.67MB / 68.67MB                                                                                                                                                                                                                                                         10.2s
 => => sha256:799f41bb59c9731aba2de07a7b3d49d5bc5e3a57ac053779fc0e405d3aed0b9e 120.17MB / 120.17MB                                                                                                                                                                                                                                                       15.9s
 => => extracting sha256:d6ff36c9ec4822c9ff8953560f7ba41653b348a9c1136755e653575f58fbded7                                                                                                                                                                                                                                                                 3.1s
 => => sha256:16b5038bccc853e96f534bc85f4f737109ef37ad92d877b54f080a3c86b3cb3a 126B / 126B                                                                                                                                                                                                                                                                8.6s
 => => extracting sha256:c958d65b3090aefea91284d018b2a86530a3c8174b72616c4e76993c696a5797                                                                                                                                                                                                                                                                 0.4s
 => => extracting sha256:edaf0a6b092f5673ec05b40edb606ce58881b2f40494251117d31805225ef064                                                                                                                                                                                                                                                                 0.4s
 => => extracting sha256:80931cf6881673fd161a3fd73e8971fe4a569fd7fbb44e956d261ca58d97dfab                                                                                                                                                                                                                                                                 3.3s
 => => extracting sha256:813643441356759e9202aeebde31d45192b5e5e6218cd8d2ad216304bf415551                                                                                                                                                                                                                                                                 3.2s
 => => extracting sha256:799f41bb59c9731aba2de07a7b3d49d5bc5e3a57ac053779fc0e405d3aed0b9e                                                                                                                                                                                                                                                                 5.5s
 => => extracting sha256:16b5038bccc853e96f534bc85f4f737109ef37ad92d877b54f080a3c86b3cb3a                                                                                                                                                                                                                                                                 0.0s
 => [builder 2/8] WORKDIR /workspace                                                                                                                                                                                                                                                                                                                      2.3s
 => [builder 3/8] COPY go.mod go.mod                                                                                                                                                                                                                                                                                                                      0.1s
 => [builder 4/8] COPY go.sum go.sum                                                                                                                                                                                                                                                                                                                      0.0s
 => [builder 5/8] COPY main.go main.go                                                                                                                                                                                                                                                                                                                    0.1s
 => [builder 6/8] COPY api/ api/                                                                                                                                                                                                                                                                                                                          0.0s
 => [builder 7/8] COPY vendor/ vendor/                                                                                                                                                                                                                                                                                                                    0.3s
 => [builder 8/8] RUN CGO_ENABLED=0 GOOS=linux GOARCH=amd64 GO111MODULE=on go build -mod=vendor -a -o manager main.go                                                                                                                                                                                                                                    19.9s
 => [stage-1 2/3] COPY --from=builder /workspace/manager .                                                                                                                                                                                                                                                                                                0.2s
 => exporting to image                                                                                                                                                                                                                                                                                                                                    0.2s
 => => exporting layers                                                                                                                                                                                                                                                                                                                                   0.2s
 => => writing image sha256:3ffb16353d202857bc2b1d0c58cfc4af0ac6c6fcab0d686c4802a54967f857ea                                                                                                                                                                                                                                                              0.0s
 => => naming to docker.io/lixueping/kububuilder-webhook:v1                                                                                                                                                                                                                                                                                               0.0s

Use 'docker scan' to run Snyk tests against images to find vulnerabilities and learn how to fix them
docker push lixueping/kububuilder-webhook:v1
The push refers to repository [docker.io/lixueping/kububuilder-webhook]
73dbf28aa4dc: Pushed 
e3d248234665: Pushed 
c0d270ab7e0d: Pushed 
v1: digest: sha256:d8a819323b504af4edc5ed9a8a6ca00ac2590a3dd6646e4ace755a1231c5e110 size: 950
➜  kubebuilder-webhook-core-types git:(master) ✗ make dry IMG="lixueping/kububuilder-webhook:v1"
/home/lxp/code/go/bin/controller-gen "crd:trivialVersions=true" rbac:roleName=manager-role webhook paths="./..." output:crd:artifacts:config=config/crd/bases
cd config/manager && kustomize edit set image controller=lixueping/kububuilder-webhook:v1
kustomize build config/default > deploy.yaml
➜  kubebuilder-webhook-core-types git:(master) ✗ make deploy IMG="lixueping/kububuilder-webhook:v1" 
/home/lxp/code/go/bin/controller-gen "crd:trivialVersions=true" rbac:roleName=manager-role webhook paths="./..." output:crd:artifacts:config=config/crd/bases
cd config/manager && kustomize edit set image controller=lixueping/kububuilder-webhook:v1
kustomize build config/default | kubectl apply -f -
namespace/kubebuilder-webhook-core-types-system created
role.rbac.authorization.k8s.io/kubebuilder-webhook-core-types-leader-election-role created
clusterrole.rbac.authorization.k8s.io/kubebuilder-webhook-core-types-proxy-role created
Warning: rbac.authorization.k8s.io/v1beta1 ClusterRole is deprecated in v1.17+, unavailable in v1.22+; use rbac.authorization.k8s.io/v1 ClusterRole
clusterrole.rbac.authorization.k8s.io/kubebuilder-webhook-core-types-metrics-reader created
rolebinding.rbac.authorization.k8s.io/kubebuilder-webhook-core-types-leader-election-rolebinding created
clusterrolebinding.rbac.authorization.k8s.io/kubebuilder-webhook-core-types-manager-rolebinding created
clusterrolebinding.rbac.authorization.k8s.io/kubebuilder-webhook-core-types-proxy-rolebinding created
service/kubebuilder-webhook-core-types-webhook-service created
deployment.apps/kubebuilder-webhook-core-types-controller-manager created
certificate.cert-manager.io/kubebuilder-webhook-core-types-serving-cert created
issuer.cert-manager.io/kubebuilder-webhook-core-types-selfsigned-issuer created
Warning: admissionregistration.k8s.io/v1beta1 MutatingWebhookConfiguration is deprecated in v1.16+, unavailable in v1.22+; use admissionregistration.k8s.io/v1 MutatingWebhookConfiguration
mutatingwebhookconfiguration.admissionregistration.k8s.io/kubebuilder-webhook-core-types-mutating-webhook-configuration created
Warning: admissionregistration.k8s.io/v1beta1 ValidatingWebhookConfiguration is deprecated in v1.16+, unavailable in v1.22+; use admissionregistration.k8s.io/v1 ValidatingWebhookConfiguration
validatingwebhookconfiguration.admissionregistration.k8s.io/kubebuilder-webhook-core-types-validating-webhook-configuration created
The Service "kubebuilder-webhook-core-types-controller-manager-metrics-service" is invalid: metadata.name: Invalid value: "kubebuilder-webhook-core-types-controller-manager-metrics-service": must be no more than 63 characters
make: *** [Makefile:43: deploy] Error 1
➜  kubebuilder-webhook-core-types git:(master) ✗ kubectl apply -f deploy.yaml     
namespace/kubebuilder-webhook-core-types-system unchanged
role.rbac.authorization.k8s.io/kubebuilder-webhook-core-types-leader-election-role unchanged
clusterrole.rbac.authorization.k8s.io/kubebuilder-webhook-core-types-proxy-role unchanged
Warning: rbac.authorization.k8s.io/v1beta1 ClusterRole is deprecated in v1.17+, unavailable in v1.22+; use rbac.authorization.k8s.io/v1 ClusterRole
clusterrole.rbac.authorization.k8s.io/kubebuilder-webhook-core-types-metrics-reader unchanged
rolebinding.rbac.authorization.k8s.io/kubebuilder-webhook-core-types-leader-election-rolebinding unchanged
clusterrolebinding.rbac.authorization.k8s.io/kubebuilder-webhook-core-types-manager-rolebinding unchanged
clusterrolebinding.rbac.authorization.k8s.io/kubebuilder-webhook-core-types-proxy-rolebinding unchanged
service/kwct-controller-manager-metrics-service created
service/kubebuilder-webhook-core-types-webhook-service unchanged
deployment.apps/kubebuilder-webhook-core-types-controller-manager unchanged
certificate.cert-manager.io/kubebuilder-webhook-core-types-serving-cert unchanged
issuer.cert-manager.io/kubebuilder-webhook-core-types-selfsigned-issuer unchanged
Warning: admissionregistration.k8s.io/v1beta1 MutatingWebhookConfiguration is deprecated in v1.16+, unavailable in v1.22+; use admissionregistration.k8s.io/v1 MutatingWebhookConfiguration
mutatingwebhookconfiguration.admissionregistration.k8s.io/kubebuilder-webhook-core-types-mutating-webhook-configuration configured
Warning: admissionregistration.k8s.io/v1beta1 ValidatingWebhookConfiguration is deprecated in v1.16+, unavailable in v1.22+; use admissionregistration.k8s.io/v1 ValidatingWebhookConfiguration
validatingwebhookconfiguration.admissionregistration.k8s.io/kubebuilder-webhook-core-types-validating-webhook-configuration configured
➜  kubebuilder-webhook-core-types git:(master) ✗ k get po -A -w
NAMESPACE                               NAME                                                              READY   STATUS              RESTARTS   AGE
cert-manager                            cert-manager-85f9bbcd97-tp6rg                                     1/1     Running             0          33m
cert-manager                            cert-manager-cainjector-74459fcc56-hljgn                          1/1     Running             0          33m
cert-manager                            cert-manager-webhook-c45b7ff-njk5w                                1/1     Running             0          33m
kube-system                             coredns-558bd4d5db-5v92s                                          1/1     Running             0          40m
kube-system                             coredns-558bd4d5db-hrtzg                                          1/1     Running             0          40m
kube-system                             etcd-kind-control-plane                                           1/1     Running             0          40m
kube-system                             kindnet-gm9n9                                                     1/1     Running             0          40m
kube-system                             kube-apiserver-kind-control-plane                                 1/1     Running             0          40m
kube-system                             kube-controller-manager-kind-control-plane                        1/1     Running             0          40m
kube-system                             kube-proxy-8j2t5                                                  1/1     Running             0          40m
kube-system                             kube-scheduler-kind-control-plane                                 1/1     Running             0          40m
kubebuilder-webhook-core-types-system   kubebuilder-webhook-core-types-controller-manager-6f66976clcw49   0/2     ContainerCreating   0          8m21s
local-path-storage                      local-path-provisioner-547f784dff-5dmrf                           1/1     Running             0          40m
kubebuilder-webhook-core-types-system   kubebuilder-webhook-core-types-controller-manager-6f66976clcw49   2/2     Running             0          8m39s
^C%
➜  kubebuilder-webhook-core-types git:(master) ✗ k logs -f -n kubebuilder-webhook-core-types-system   kubebuilder-webhook-core-types-controller-manager-6f66976clcw49 manager
2022-03-22T14:57:49.855Z        INFO    controller-runtime.metrics      metrics server is starting to listen    {"addr": "127.0.0.1:8080"}
2022-03-22T14:57:49.856Z        INFO    controller-runtime.webhook      registering webhook     {"path": "/validate-core-v1-pod"}
2022-03-22T14:57:49.856Z        INFO    controller-runtime.webhook      registering webhook     {"path": "/mutate-core-v1-pod"}
2022-03-22T14:57:49.856Z        INFO    setup   starting manager
I0322 14:57:49.856449       1 leaderelection.go:242] attempting to acquire leader lease  kubebuilder-webhook-core-types-system/78e545c5.github.com...
2022-03-22T14:57:49.856Z        INFO    controller-runtime.manager      starting metrics server {"path": "/metrics"}
2022-03-22T14:57:49.856Z        INFO    controller-runtime.webhook.webhooks     starting webhook server
2022-03-22T14:57:49.856Z        INFO    controller-runtime.certwatcher  Updated current TLS certificate
2022-03-22T14:57:49.857Z        INFO    controller-runtime.webhook      serving webhook server  {"host": "", "port": 9443}
2022-03-22T14:57:49.857Z        INFO    controller-runtime.certwatcher  Starting certificate watcher
I0322 14:57:49.865484       1 leaderelection.go:252] successfully acquired lease kubebuilder-webhook-core-types-system/78e545c5.github.com
2022-03-22T14:57:49.865Z        DEBUG   controller-runtime.manager.events       Normal  {"object": {"kind":"ConfigMap","namespace":"kubebuilder-webhook-core-types-system","name":"78e545c5.github.com","uid":"9cf30dd0-8383-4e2c-98fc-45263b782d2d","apiVersion":"v1","resourceVersion":"5285"}, "reason": "LeaderElection", "message": "kubebuilder-webhook-core-types-controller-manager-6f66976clcw49_f8585ec5-61e5-40a4-a79f-aa3ad8f597e0 became leader"}
```
Once the image push success, we need to do a couple of things before moving onto the deploy section, please remove the lines between 3 and 9 webhookcainjection_patch.yaml which is under the config/default folder because we are not creating MutatingAdmissionWebhook here, and remove line 16 from the kustomization.yaml which is under the same directory. Also, remove line 2 from the kustomization.yaml which is under config/rbac directory, and, you’re all set.
The last thing that we should do here is enabling and deploying the cert-manager, in order to do that we should edit the “config/default/kustomization.yaml” file by uncommenting the sections marked by [WEBHOOK] and [CERTMANAGER] comments.

We know that kubebuilder also uses a cert-manager to manage TLS management for our webhook, so, we should install a cert-manager in our cluster first, let’s do this.

Yaay!!! Seems everything is working, but let’s test the webhook by creating Pod which has no required annotation on it.
# test with invalid Pod

```
➜  kubectl run nginx --image=nginx
Error from server (missing annotation example-mutating-admission-webhook): admission webhook "mpod.kb.io" denied the request: missing annotation example-mutating-admission-webhook
➜  kubectl run nginx --image=nginx  --overrides='{ "apiVersion": "v1", "metadata": {"annotations": { "example-mutating-admission-webhook":"foo" } } }'
pod/nginx created
➜  ~ k get po nginx -o yaml
apiVersion: v1
kind: Pod
metadata:
  annotations:
    example-mutating-admission-webhook: foo
  creationTimestamp: "2022-03-22T15:06:02Z"
  labels:
    its: start  <== expected
    mj: thisistheend <== expected
    run: nginx
  name: nginx
  namespace: default
  resourceVersion: "6730"
  uid: c72bf6f9-cb14-4d3e-9b60-cb7754edaf65
spec:
  containers:
  - image: nginx
    imagePullPolicy: Always
    name: nginx
    resources: {}
    terminationMessagePath: /dev/termination-log
    terminationMessagePolicy: File
    volumeMounts:
    - mountPath: /var/run/secrets/kubernetes.io/serviceaccount
      name: kube-api-access-m9bxz
      readOnly: true
```
Now, we proved that everything is working as we expected 🎉🎉🎉


# References

> https://book.kubebuilder.io/reference/webhook-for-core-types.html

> https://medium.com/trendyol-tech/getting-started-to-write-your-first-kubernetes-admission-webhook-part-2-48d0b0b1780e

> https://medium.com/swlh/extending-kubernetes-part-2-mutating-webhook-54076097afeb

> https://pkg.go.dev/sigs.k8s.io/controller-runtime/pkg/webhook/admission#PatchResponseFromRaw

> https://github.com/kubernetes-sigs/controller-runtime/blob/master/pkg/webhook/admission/webhook.go