sudo yum update -y
sudo yum install wget -y
sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
sudo yum install docker-ce
sudo yum install docker
sudo usermod -aG docker ec2-user
sudo systemctl start docker
sudo systemctl enable docker
systemctl status docker
sudo rpm -qa |grep docker
docker images
docker pull centos
$ sudo groupadd docker
$ sudo usermod -aG docker ec2-user
$ grep ^docker /etc/group
dockerroot:x:995:
docker:x:1001:ec2-user
sudo yum-config-manager --enable "Red Hat Enterprise Linux Server 8 Extra(RPMs)"
sudo subscription-manager repos --enable rhel-8-server-extras-rpms
hello-openshift

Redhat 
https://linuxconfig.org/how-to-install-docker-in-rhel-8
The dnf config-manager utility let us, among the other things, easily enable or
 disable a repository in our distribution. By default, only the appstream and baseos 
repositories are enabled on Rhel8; we need to add and enable also the docker-ce repo.
 All we need to do to accomplish this task, is to run the following command:
step1:-$ sudo dnf config-manager --add-repo=https://download.docker.com/linux/centos/docker-ce.repo
We can verify that the repository has been enabled, by looking at the output of the following command:
step2:-sudo dnf repolist -v
step3:-
Installing docker-ce:-
$ dnf list docker-ce --showduplicates | sort -r
step4:-
Install a specific version of docker-ce
$ sudo dnf install docker-ce-3:18.09.1-3.el7
Force the installation of docker-ce with the --nobest option
$ sudo dnf install --nobest docker-ce
Install the latest available containerd.io package manually
$ sudo dnf install https://download.docker.com/linux/centos/7/x86_64/stable/Packages/containerd.io-1.2.6-3.3.el7.x86_64.rpm

step6:-
Start and enable the docker daemon

Once docker-ce is installed, we must start and enable the docker daemon, so that it will be also launched automatically at boot. The command we need to run is the following:

$ sudo systemctl enable --now docker

At this point, we can confirm that the daemon is active by running:

$ systemctl is-active docker
active

Similarly, we can check that it is enabled at boot, by running:

$ systemctl is-enabled docker
enabled

Installing docker-compose

Docker compose is a very useful package which let us manage multi-container applications, like for example those based on the LAMP stack, where each part of the environment (PHP, Apache, MariaDB) is provided by a dedicated container (if you are interested in the subject, take a look at our tutorial about creating a docker-based lamp stack). The package is not available on Rhel8, nor an equivalent exists to be used with the Rhel tools. It's, however, possible to install it in many ways: just keep on reading and decide what suits you best.
Global installation

The way we should install docker-compose varies depending on whether we want to install it globally or just for a single user. At the moment of writing, the only way to install it globally is to download the binary from the github page of the project:

$ curl -L "https://github.com/docker/compose/releases/download/1.23.2/docker-compose-$(uname -s)-$(uname -m)" -o docker-compose

Once the binary is downloaded, we move it into /usr/local/bin and we make it executable:

$ sudo mv docker-compose /usr/local/bin && sudo chmod +x /usr/local/bin/docker-compose








///////////////////////
sudo docker ps
sudo docker ps -a
sudo docker conatiner ls
sudo docker conatiner ls -a
sudo docker images
sudo docker run -dit --name mydemoconatiner -P fedora /bin/bash
sudo docker  ps
how attached container
sudo docker attach conatainerid
 df -h
cat /etc/redhat-release
ctrl +d outside from bash
sudo docker start containerid
https://kubernetes.io/docs/tutorials/kubernetes-basics/create-cluster/cluster-intro/
https://upbasiceduboard.gov.in/


/////////////////////////
sudo wget https://mirror.openshift.com/pub/openshift-v4/clients/oc/4.2/linux/oc.tar.gz
ls -ltr
tar -xvzf oc.tar.gz
ls -ltr
echo $PATH
cp oc /usr/local/sbin
cd /usr/local/sbin
ls -la
Log in with this token
 go to portal  and taken token from cli:-
oc login --token=e0LadC-PFzkiSUryTnybumqZPeaCnoNfAXv64J242HA --server=https://api.us-east-1.starter.openshift-online.com:6443

oc new-project <projectname>
oc new-app django-psql-example
kubectl create deployment hello-node --image=gcr.io/hello-minikube-zero-install/hello-node



tomcat-dev

stage('Deploy to Tomcat'){
      
      sshagent(['tomcat-dev']) {
         sh 'scp -o StrictHostKeyChecking=no target/*.war ec2-user@13.232.63.219:/usr/share/tomcat8/webapps'
      }
   }


sh 'scp -i /home/ec2-user/tomcat.pem  **/target/*.war ec2-user@13.232.63.219:/usr/share/tomcat8/webapps'
      }
AKCp5fUYgM9xy3PayY4KcQ95qdiNGqs5qcm6Rxu9a3BGVeR7W8tFF2rU9Us48kasNnaSpi1c9



