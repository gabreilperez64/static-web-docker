# External resources used for this excercise 
- Static website from https://github.com/GNiruthian/Europe-Travel-Website-html-css-js
- Deploying a Static HTML Site with Docker and Nginx: https://medium.com/@zul.m/deploying-a-static-html-site-with-docker-and-nginx-6f5bcdcbc650
- https://docs.docker.com/engine/reference/commandline/push/
- https://support.terra.bio/hc/en-us/articles/360035638032-Publish-a-Docker-container-image-to-Google-Container-Registry-GCR
- https://git-scm.com/docs

# Requirements
Deploy a static website with auto-scalability, automating the life cycle management of containers and the app should be set behind a load balancer with an external endpoint, so it can be accessed globally. 

# Sprint 1
The Docker image should be running locally and pushed to a Container Registry or Artifact Registry. 
# Steps followed for Sprint 1
1. Checking active services: gcloud services list
2. Clone the repository: git clone https://github.com/GNiruthian/Europe-Travel-Website-html-css-js
3. Create a Docker directory: mkdir Docker 
4. Access the directory: cd Docker/
5. Create a Docker file with your preferred service (nginx:alpine):
FROM service-name 
COPY . /usr/share/nginx/html
6. Build the Docker Image for the HTML Server: docker build -t html-server-image:v1 .
Tip: You can list your images using: docker images
7. Run the Docker Container: docker run -p 8087:80 image-name
Tip: You can test your deployment using http://localhost:8087/ 


# Sprint 2
The website should be Public on the web through a load balancer with an external endpoint.  
# Steps followed for Sprint 2
1. Tag image with registry name: docker tag [IMAGE] gcr.io/[PROJECT-ID]/[IMAGE]
2. Push your image to Google Container Registry (private): docker push gcr.io/[PROJECT-ID]/[IMAGE]
3. Create a Google Kubernetes Engine Cluster: https://cloud.google.com/kubernetes-engine/docs/tutorials/hello-app#creating_a_cluster
4. Deploying the sample app to Google Kubernetes Engine https://cloud.google.com/kubernetes-engine/docs/tutorials/hello-app#deploying_the_sample_app_to
5. Exposing the app to the internet: https://cloud.google.com/kubernetes-engine/docs/tutorials/hello-app#exposing_the_sample_app_to_the_internet


# Sprint 3
The Capstone project is completed and the group’s repository in GitHub is publicly available with a proper README file explaining the project and pointing out the original repository used for it. [1] as well a file.log containing the output of every commit of the repository.p
1. Several commands where used to push the repository, which you can also see from the "file.log" file.
