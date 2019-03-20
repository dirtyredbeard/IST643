# Containers and Development Operations: Part 1, Local Development Workflows <!-- omit in toc -->

> Estimated Completion Time: 5-10 Hours
>
> Due Date: You should have an understanding of these concepts by next class.

## Learning Objective <!-- omit in toc -->

To garner a deeper understanding of container-based development, the services required to effectively offer a container based web application\service, and to sharpen your basic systems administration skills.

In this lab you will:

- Tweak, build, and deploy a web application.
- Setup a proxy between Docker and Kubernetes
- Use a local image registry
- Deploy Jenkins
- Utilize Git and Jenkins to delpoy a web application

## Prepare our environment

At this juncture you should have the following up and running:

- Kubernetes (Minikube)
- Image Repository
- Minikube Dashboard

## Lab Task List

### Lets Build and Push Jenkins

- [ ] Use Docker to build and add a Jenkins Image to our Kubernetes registry
  - [ ] The Dockerfile is found in applications/jenkins/Dockerfile --read it!
    - [ ] Ensure nothing else is running on this port
        > docker build -t 127.0.0.1:30400/jenkins:latest -f applications/jenkins/Dockerfile applications/jenkins
- [ ] Run your Socat Proxy, we'll need that to add the image to the repository
- [ ] Push your Docker image to the registry
- [ ] Ensure your Jenkins image is in your registry
- [ ] Stop your proxy

### Deploy and Configure Jenkins

- [ ] Use `kubectl` to apply the 'jenkins.yaml' in the manifests directory
  - [ ] Check the status of your deployment using `kubectl rollout status deployment/jenkins`
- [ ] After the rollout is complete, use `kubectl` to list the pods in our cluster
- [ ] Have minikube start the jenkinks service
- [ ] Note the secret\password that Jenkins is using
  
> kubectl exec -it `kubectl get pods --selector=app=jenkins --output=jsonpath={.items..metadata.name}` cat /var/jenkins_home/secrets/initialAdminPassword

- [ ] Open Jenkins in the web browser!
  - [ ] Give Jenkins the admin password, and accept the plugin installation.
    - [ ] What did that plugin do though?!?
  - [ ] Create a user
  - [ ] Kind: Kubernetes configuration (kubeconfig)
  - [ ] ID: kenzan_kubeconfig
  - [ ] Kubeconfig: From a file on the Jenkins master: `/var/jenkins_home/.kube/config`
- [ ] Create a pipeline that:
  - [ ] Is named `Hello-Kenzan Pipeline`
  - [ ] Uses source code managment: Git
  - [ ] Connects to your Github account
  - [ ] Uses the `kubernetes-ci-cd/Jenkinsfile`  file as the script file (root of our forked repository)
  - [ ] Save and Build!
    - [ ] After a few minutes you should see your Build, Push and Delpy stages go green.
    - [ ] Start the hello-kenzan service!

You will notice that the page rendered in your browser does not reflect the changes which you had previously made to your website --we have not yet pulled in those changes. We have told minikube to deploy directly from Github --not the local changes we made in the previous lab.

### Continuous Integration

- [ ] Tweak your hello Kenzan index.html file again
  - [ ] Add some text, like: `Please, I hope this works!`
- [ ] Use git to add a message and commit all of your changes
- [ ] Use git to push those changes
- [ ] In the browser, tell Jenkins to build your application
- [ ] View your changes! `minikube service hello-kenzan`

## Questions

Come to class able to describe what each configuration file is configured to do!