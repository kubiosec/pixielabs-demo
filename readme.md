# Setting up a pixielabs demo
![Welcome](https://github.com/kubiosec/pixielabs-demo/raw/main/images/Screenshot%202021-05-06%20at%2011.59.32.png)

## 1. Setting up a k8s cluster
For the sake of this demo I will be using a managed kubernetes cluster on the DigitalOcean platform. 
It should work on other clusters to. I tested also on a self managed kubeadm cluster on AWS.
Make sure your nodes have enough memory available. (8G or so)

## 2. Verify access to cluster
```
export KUBECONFIG=.....
kubect get no -o wide
```
## 3. Install a demo application 
See https://github.com/xxradar/app_routable_demo, but any microservice demo app should work of course.
```
git clone https://github.com/xxradar/app_routable_demo.git
cd ./app_routable_demo
./setup.sh
watch kubectl get po -n app-routable-demo
```
## 4. Installing pixielabs.ai 
### 1. Install the PX CLI
See https://docs.pixielabs.ai/
```
bash -c "$(curl -fsSL https://withpixie.ai/install.sh)"
```
When you are installing on Mac, your browser window will open automatically asking you to sign in with a Google account.
Return to the CLI and complete the instructions
```
px deploy
```
If you are using a non-supported cluster type, chances are that it will work as I tested it on DigitalOcean.<br>
Follow the instructions.<br>
When finished, open a browser and access https://work.withpixie.ai/<br>
Done !!!
