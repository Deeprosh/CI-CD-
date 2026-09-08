# How to answer CI/CD implementation when asked in interview?

<img width="1833" height="951" alt="image" src="https://github.com/user-attachments/assets/c9325808-67dd-4017-95e2-d0f3246348cc" />


## First choose VCS platform to import the source code and select the target system to implement the CI/CD pipleine as kubernetes
- we use github as our source code repository and our target platform as kubernetes.
- lets say the user tries to do the code commit and creates the code commit in vcs as selects the github as source code repository.
- we use an ci/cd orchestrator like jenkins, why we use orchestrator is whenever there is a code commit to github repository, git webhook triggers the pipeline in the orchestrator. 
- Using jenkins we will implement CI, and it has multiple stages.As part of the first stage in jenkins piepeline, we will checkout the code.what is the code that we are checking out here is the code commit that user has made.
- we will try to perform a build action along with unit test cases.In the same state some people alos perform static testing. we use maven for the building and we use unit test cases in the code repository, if its java application.
- If its python or node.js we can convert the unit testing framework and build language accordingly.
- once this is done, then we will move towards code scanning.we can use sonarqube for code scanning solutions. we will scan the code for any security vulnerabilities or even for the static code analysis in this stage. At this stage we perform some secutity checks to ensure our code is free from any security vulnerabilites.
- Image building-because the target platform is kubernetes we will build container image in this stage.For that we will use dockerfile in the github reposiroty.
- Once this is done we need to do image scanning,through which we will verify the image that we have crated has any vulnerabilites.we have to verify base image and overall image is free from vulnerabilites.
- Finally we will push this image to image registry it can be dockerhub, ECR etc.,These ar multiple stages that we have in continous integration and we write jenkins file in jenkins for orchestrating each of them.
- How do we write them, we write them using declaravtive pipelines which are easily to collobrate wiyth grrovy scripting part.
- Once the image is pushed,we will create different repository in github for image manifests to get this image into kubernetes platform.
- we can use the same jenkins pipeline that we have created and update this image in the kubernetes YAML manifest.
- we need to again the push this updated image to a github repository which is hosting all of this kubernetes manifest.
- once this done,gitops approach or argo cd approach, we will deploy the new changes to the kubernetes platform.
- How do we do that, argo cd is continously watching the manifest repository.wherever you are pushing the updated k8s YAML manifests, there you have to configure argo cd to watch this git repository and push the changes to the kubernetes cluster.
