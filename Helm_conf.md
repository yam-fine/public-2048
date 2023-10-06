#configure helm to manage the kubernetes cluster  

helm repo add eks https://aws.github.io/eks-charts  

helm repo update eks  

helm install aws-load-balancer-controller eks/aws-load-balancer-controller \            
  -n kube-system \
  --set clusterName=cluster-1 \
  --set serviceAccount.create=false \
  --set serviceAccount.name=aws-load-balancer-controller \
  --set region=us-east-1 \
  --set vpcId=vpc-060862115eb0f134b  
