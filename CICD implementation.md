# How to answer CI/CD implementation when asked in interview?

<img width="1833" height="951" alt="image" src="https://github.com/user-attachments/assets/c9325808-67dd-4017-95e2-d0f3246348cc" />


## First choose VCS platform to import the source code and select the target system to implement the CI/CD pipleine as kubernetes
- we use github as our source code repository and our target platform as kubernetes.
- lets say the user tries to do the code commit and creates the code commit in vcs as selects the github as source code repository.
- we use an ci/cd orchestrator like jenkins, why we use orchestrator is whenever there is a code commit to github repository, git webhook triggers the pipeline in the orchestrator. 
- Using jenkins we will implement CI, and it has multiple stages.As part of the first stage in jenkins piepeline, we will checkout the code.what is the code that we are checking out here is the code commit that user has made.
- 
