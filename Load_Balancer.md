#Configure the application load balancer

ALB Controller

eksctl utils associate-iam-oidc-provider --cluster cluster-1 --approve

curl -O https://raw.githubusercontent.com/kubernetes-sigs/aws-load-balancer-controller/v2.5.4/docs/install/iam_policy.json
