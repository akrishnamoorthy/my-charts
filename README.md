
# my-charts
The repository here consists of the helm templates and a values.yaml file .
The values.yaml file consists of values for variables( environment specific configurations, replica count etc ) which could be different for different environments.
To install this locally download this repository and run helm install

This is the helm files needed to deploy a search application using SOLR 
The code for the search application can be found here https://github.com/akrishnamoorthy/search

The application needs a SOLR server.

**To install solr :**

helm install bitnami/solr
kubectl config set-context --current --namespace=solr
kubectl port-forward --namespace solr svc/solr 8983:8983 
echo Password: $(kubectl get secret --namespace solr solr -o jsonpath="{.data.solr-password}" | base64 --decode)
![image](https://user-images.githubusercontent.com/1224501/141647537-165b9dc0-d66d-45e5-8d49-9aab6da19250.png)

**To install search application using helm**

Checkout this repository
Go to the root and do helm install as accountsearch

<img width="1470" alt="Screenshot 2021-11-13 at 7 42 16 PM" src="https://user-images.githubusercontent.com/1224501/141647144-8166fbb7-17b9-4c69-879b-f501342625c9.png">

<img width="1153" alt="Screenshot 2021-11-13 at 7 47 05 PM" src="https://user-images.githubusercontent.com/1224501/141647175-03d576d9-87cc-4b91-a5d2-96e8d732bf0a.png">

Run kubectl port-forward service/as-accountsearch 8080:80






