#Configure the application load balancer

ALB Controller  

eksctl utils associate-iam-oidc-provider --cluster cluster-1 --approve  

curl -O https://raw.githubusercontent.com/kubernetes-sigs/aws-load-balancer-controller/v2.5.4/docs/install/iam_policy.json  

aws iam create-policy --policy-name AWSLoadBalancerControllerIAMPolicy --policy-document file://iam_policy.json  

#Attach the role  
eksctl create iamserviceaccount \  
  --cluster=<your-cluster-name> \  
  --namespace=kube-system \  
  --name=aws-load-balancer-controller \  
  --role-name AmazonEKSLoadBalancerControllerRole \  
  --attach-policy-arn=arn:aws:iam::<your-aws-account-id>:policy/AWSLoadBalancerControllerIAMPolicy \  
  --approve  
