# 13.Kubernetes.Data.Secrets

I updated the manifest from the previous task: I added `initContainers` logic, a shared `emptyDir` volume for exchanging the generated file, and a section to mount SSH keys from a `SealedSecret` for the root user.


```
Expected result: Due to load balancing, you will see different pod names in the tags.
<h1>nginx-deployment-xxxx-xxxx</h1>.
```
<img width="975" height="372" alt="image" src="https://github.com/user-attachments/assets/752aeb8f-be11-42ef-be15-0e23e60803a2" />

The private and public keys were encrypted using the cluster's kubeseal, and only the secure SealedSecret manifest was added to the repository.

<img width="975" height="203" alt="image" src="https://github.com/user-attachments/assets/0877825e-b858-4d98-abe9-9a6cc77094c9" />
```
kubectl get sealedsecret
```
<img width="975" height="491" alt="image" src="https://github.com/user-attachments/assets/887bae41-1054-4b40-93fc-2ec3a601f391" />


