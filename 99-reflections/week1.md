# Week 1 Reflection – NGINX Pod and Deployment

This week, I worked through the Kubernetes fundamentals lab where I deployed a basic NGINX web server using both a Pod and a Deployment. I also learned about security contexts and how to scale workloads.

---

## ✅ What I Learned

- `kind` writes to the kubeconfig file.
when it created the cluster, it also injects to the `clusters`, `contexts`, `current-context` and `users` config keys:
```
╰─❯ kubectl config view --minify
apiVersion: v1
clusters:
- cluster:
    certificate-authority-data: DATA+OMITTED
    server: https://127.0.0.1:37665
  name: kind-grow-lab
contexts:
- context:
    cluster: kind-grow-lab
    user: kind-grow-lab
  name: kind-grow-lab
current-context: kind-grow-lab
kind: Config
preferences: {}
users:
- name: kind-grow-lab
  user:
    client-certificate-data: DATA+OMITTED
    client-key-data: DATA+OMITTED
```
This was the reason why `kubectl get nodes` was able to magically discover the cluster created using `kind`.
the `clusters[0].server` at port `:37665` which is mapped to `:6443` internally in the docker container, is the kube API server.

We can curl its `/version` endpoint to inspect some version info:
```
╰─❯ curl --insecure https://127.0.0.1:37665/version
{
  "major": "1",
  "minor": "33",
  "emulationMajor": "1",
  "emulationMinor": "33",
  "minCompatibilityMajor": "1",
  "minCompatibilityMinor": "32",
  "gitVersion": "v1.33.1",
  "gitCommit": "8adc0f041b8e7ad1d30e29cc59c6ae7a15e19828",
  "gitTreeState": "clean",
  "buildDate": "2025-05-15T08:19:08Z",
  "goVersion": "go1.24.2",
  "compiler": "gc",
  "platform": "linux/amd64"
}%

```

- 
- 
- 


---

## ❓ What Was Challenging

- 
- 
- 

---

## 🧪 Commands I Practiced

```bash




```

---

## 🔐 Security Improvements I Made

- 
- 

---

## 📝 Questions I Still Have

- wth are helmcharts
- wen argocd
- 

---

## 📎 Related YAMLs

- `nginx-pod.yaml`
- `nginx-deployment.yaml`

---

## 🚀 Looking Ahead

I’m excited to explore GitOps in Week 2 and automate deployments using FluxCD.

