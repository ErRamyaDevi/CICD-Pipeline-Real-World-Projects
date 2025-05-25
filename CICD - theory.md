Continuous Delivery:-
DEV---->QA----->Staging(UAT) ----->Production
Continous delivery is a practice where code changes are automatically prepared for a release to production.

CICD Process (Continuous Integration (build & QA) and Continuous Deployment (Staging & Production) Process needed to meet Continuous delivery requirements.

CICD process has two parts:---> Build Pipeline and Deployment Pipeline to form an end-to-end pipeline which is called as CICD pipeline. Every step is automated so it is called CICD Pipeline.
automate and secure 
Build means -->source code of a program converted into a product/artifact which can be consumed by QA/Customer

Continuous Integration:-
CI is a practice that helps to frequently integrate code changes into a central repository and then automate builds.
+ Find bugs faster
+ faster releases
+ Improves Quality

Production Grade **BUILD** Pipeline Stages
DEVSECOPS---> Applying security over anything becomes devsecops.

These 9 stages are similar to any kind of programming code you deploy. example: For Java you'll get .jar file as artifact and any other language you may get as zip file or tar file as artifact.
Stage 1: Build & Unit Test
  + Generate artifacts
  + Unit Test - Here Unit Test performs on total source code which integrates all files at a single point of time which is different from developer's unit test.
    **Tools Used: Maven**

Stage 2: Code Coverage
  + How many lines of code you tested?
    Sometimes, 4 test cases which you undergone in previous Unit Test stage could not be reliable and we cannot maintain quality of code for remaining number of lines. Those 4 test cases only include 600 lines of code to test its functionality.
  + Unused code
    **Tools Used: Jacoco**

Stage 3: Software Composition analysis /static analysis (this step can be done even before build as it just checks the raw code)
    +Identify Vulnerabilities introduced by open-source while copying or 3rd party libraries used in code.
    +In order to prevent license issue or dependency issue which is not owned by our company.
    **Tools Used: OWASP Dependency-check**
    Web Application Security

Stage 4: Static Application Security Testing ( we are using application to scan and *NOT RUNNING* application)
    + Identify vulnerabilities in our own proprietary code
    + Insecure coding practices
    **Tools Used: Sonarqube** (SAST scanner) (It helps to run scanning against various coding languages.

Stage 5: Quality Gates
Combining code coverage, SCA, Sonarqube scan we are performing a quality standards (in percentage levels) to get a Quality code against code coverage, code vulnerabilities, code scan.
  + check if application meets the quality standards.
    **Tools Used: Sonarqube Quality Profile**

if the code doesn't meet the quality gate standards, then we should inform the developer to fix the code --> intention of the cicd integration.
sonarqube dashboard collects all the three results code coverage,SCA & SAST

Stage 6: Build Image:
 + Generate a deployable artifact
   **Tools Used: Dockerfile**

Stage 7: Scan Docker Image:
+ Identify Vulnerabilities in image layers such as OS Layer,Dependency Layer, Application Layer



    
