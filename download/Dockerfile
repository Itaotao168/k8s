FROM tomcat
MAINTAINER tao.mei <4836266@qq.com>
RUN  cd /tmp &&  curl -O https://raw.githubusercontent.com/coreos/flannel/master/Documentation/kube-flannel.yml
RUN  cd /tmp &&  curl -O https://raw.githubusercontent.com/kubernetes/dashboard/v2.0.3/aio/deploy/recommended.yaml
##ingress
RUN  cd /tmp &&  curl -O https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v0.35.0/deploy/static/provider/cloud/deploy.yaml
RUN cd /tmp/ && curl -o service-nodeport.yaml https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v0.35.0/deploy/static/provider/baremetal/deploy.yaml


