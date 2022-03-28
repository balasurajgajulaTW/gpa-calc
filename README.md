
# A web app built with flutter

- Build Job commands
```
echo "-----BUILDING DOCKER IMAGE-----"
cd .
docker build -t balasurajgajulatw/gpa-calc .
docker push balasurajgajulatw/gpa-calc
echo "-----BUILT DOCKER IMAGE AND PUSHED INTO DOCKER REGISTRY-----"
```

- Test Job commands
```
echo "-----TESTING SYNTAX CHECK FOR index.html-----"
brew install tidy-html5
cd .
tidy index.html
echo "-----DONE TESTING-----"
```

- Deploy Job commands
```
echo "-----CREATING A DEPLOYMENT IN KUBERNETES-----"
kubectl create deployment  gpa-calc --image=balasurajgajulatw/gpa-calc --replicas=2 --port=80
kubectl expose deployment gpa-calc --port=80 --target-port=80 --type=NodePort
minikube service gpa-calc --url
echo "-----DEPLOYMENT DONE-----"
```


