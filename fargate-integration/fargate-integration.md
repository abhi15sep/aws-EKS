# Fargate integration into EKS

## create new EKS cluster, Fargate enabled

## add Fargate support to existing EKS cluster

```bash
eksctl create fargateprofile -f ./fargate-profile.yaml
```

=================
> Create fargate cluster on EKS

1. create eks cluster with fargate
```bash
eksctl create cluster -f ./eks-course-with-fargate.yaml
```

kubectle get nodes
kubectl get pods --all-namespaces

2. Launch an nginx pod
kubectl run mginx --image=nginx --restart=Never

3. Cleanup
ekctl get cluster
ekctl delete cluster --name EKS-Fargate-course-cluster

=====================
> Add fargate capability to existing eks cluster

1. Go to IAM > create role > EKS > EKS- Fargate Pod > Then create role.

2. Create 2 namespaces.
kubectl create namespace fargatedemo
kubectl create namespace staging

3. Create add-fargate-profile.yaml
```bash
eksctl create fargateprofile -f ./add-fargate-profile.yaml
``` 

4. run nginx pod in namespace fargatedemo
kubectl run nginx --image=nginx --restart=Never --namespace=fargatedemo