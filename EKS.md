eksctl create cluster --name cluster-1 --region us-east-1 --fargate

aws eks update-kubeconfig --name cluster-1 --region us-east-1
