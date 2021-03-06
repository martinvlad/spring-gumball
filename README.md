# Lab 10 - DevOps CI/CD

## Part 1 (CI)
For part 1, I created a CI workflow and once I pushed a commit, this triggered the action.
<img width="1400" alt="part1CIworkflow" src="https://user-images.githubusercontent.com/36089262/118377404-e27a3300-b581-11eb-9434-46c7dda3c1e0.png">


## Part 2 (CD)

I first begin by creating all the necessary secrets in my workspace, one of them being the GKE_PROJECT and the other being GKE_SA_KEY. To do so, I need to go to GCP Service Accounts and create an account.

<img width="1440" alt="serviceacc" src="https://user-images.githubusercontent.com/36089262/118378899-a0ee8580-b58b-11eb-8ba4-17e521f3fae9.png">

<img width="1440" alt="googlekey" src="https://user-images.githubusercontent.com/36089262/118378892-959b5a00-b58b-11eb-8f9a-829e9b636123.png">



I then enter both of these secrets in my github project secrets settings.
<img width="1440" alt="gke_project_gke_sa_key" src="https://user-images.githubusercontent.com/36089262/118378884-89170180-b58b-11eb-87dd-40cecd23e978.png">

First, I make sure I have my cluster up and running.
<img width="1440" alt="cluster" src="https://user-images.githubusercontent.com/36089262/118380211-ebc0cb00-b594-11eb-86e8-4f0db6fb74f9.png">

I then proceed to deploy to GKE with a release.
<img width="1440" alt="gke_deploy" src="https://user-images.githubusercontent.com/36089262/118378912-b499ec00-b58b-11eb-810d-2eccbbc74d38.png">

Continuing to build to deploy on GKE.
<img width="1440" alt="gke_build" src="https://user-images.githubusercontent.com/36089262/118378917-bd8abd80-b58b-11eb-8ec2-4f199de7126b.png">

On version 2.4 I forgot to set permissions to the service account, so the build failed. However, once I added them in 2.5, it worked and I successfully deployed to GKE.
<img width="1440" alt="2 5" src="https://user-images.githubusercontent.com/36089262/118380045-f595fe80-b593-11eb-8ec0-fc913362151a.png">

<img width="1440" alt="successfuldeploy" src="https://user-images.githubusercontent.com/36089262/118379763-d72f0380-b591-11eb-860e-a9b348778254.png">


Services and Ingress
<img width="1440" alt="services_and_ingress" src="https://user-images.githubusercontent.com/36089262/118379723-5b34bb80-b591-11eb-9b74-32de7c91c613.png">
Workloads
<img width="1440" alt="workloads" src="https://user-images.githubusercontent.com/36089262/118379727-62f46000-b591-11eb-9fd6-6a63c189fe28.png">

Finally, we create a load balancer.
<img width="1440" alt="spring-gumball-lb" src="https://user-images.githubusercontent.com/36089262/118379720-4c4e0900-b591-11eb-8599-3581e7e577af.png">

Successful creation.
<img width="1440" alt="ingress_success_1" src="https://user-images.githubusercontent.com/36089262/118379899-fb3f1480-b592-11eb-9d76-97d9c4b48ca2.png">

<img width="1440" alt="Ingress_details" src="https://user-images.githubusercontent.com/36089262/118379827-6cca9300-b592-11eb-884d-ec347748f09a.png">

If we take a look in the browser, it works perfectly.
<img width="1439" alt="ingress_successful" src="https://user-images.githubusercontent.com/36089262/118379817-5cb2b380-b592-11eb-9103-9d6b2c8d6e0a.png">


