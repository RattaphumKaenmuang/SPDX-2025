# DevOps
Became mainstream in the industry after John Allspaw and Paul Hammond yapped at Velocity Conference in 2009 under the topic **"10 Deploys per Day: Dev and Ops Cooperation at Flickr"**, integrating the Development team and the Operation team together, becoming "DevOps".

* Operations - seeks organizational stability
* Developers - seek change
* Testers - seek risk reduction

![DevOps](https://upload.wikimedia.org/wikipedia/commons/thumb/0/05/Devops-toolchain.svg/1200px-Devops-toolchain.svg.png)

## Steps
### 1. Plan
* Deployment **Plans**
* Gitlab
### 2. Create
* Get solution (not necessarily code)
* Python
### 3. Verify
* Tests
  * DAST (Dynamic Application Security Test)
  * SAST (Static Application Security Test)
* Pytest
### 4. Package
* Put things together
* Docker
### 5. Release
* Version
* Gitlab
### 6. Configure
* Deployment
* k8s
### 7. Monitor
* Check metrics (health check, resource monitoring, logs, etc.)
* Grafana / Prometheus

## 7 Ways to Get Started with DevOps
* Invite Your Operations Team Into Your Development Process
* Visualize the Work Together
* Automate Your Test/Build Process => (CI/CD)
* Create a Deployment Plan
* Identify Fragile Systems
* Smooth Out Wait States
* Link Your Work to Your Value

## Everything as Code
Do everything as code idk, I have to fill the word count.
* Infrastructure as Code (IaC)
  * Setup environment and infrastructure using code instead of manually configuring it like an unclean peasant
* Diagram as Code
  * You're probably just tweaking or something
* Presentation Slide as Code
  * You're probably just tweaking or something 2

## CI/CD
* Continuous Integration (CI)
Use automation tools that empower development teams to build and test code after each merge
* Continuous Deployment (CD)
  * or Continuous Delivery (CD)
  * Focused on keeping the code ready to deploy
  * Make sure all the sets of features are **ready to go** and the latest build is ready to be delivered at any time given