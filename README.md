# kube-aws-controller-skipper-ingress

This repo deploys a [kube-ingress-aws-controller](https://github.com/zalando-incubator/kube-ingress-aws-controller) and [skipper-ingress ](https://github.com/zalando/skipper) to EKS.

### The necessary prerequisites are to: <br>
1.  Tag the worker node groups / cluster securitygroup with `kubernetes:application=kube-ingress-aws-controller`. If using multiple ingress controllers and ``--cluster-id` is set, then tag the securitygroup with `kubernetes:application=${cluster-id}`.
2. Subnets need to be tagged with:<br>
- public subnets: `kubernetes.io/role/elb=1`
- private subnets: `kubernetes.io/role/internal-elb=1`
3. Open incoming ports on the worker nodes for port `9999`. 

### To deploy the helm chart
Run: <br>
`../skipper-ingress-kube-aws-controller $ helm install ${release-name} .`
