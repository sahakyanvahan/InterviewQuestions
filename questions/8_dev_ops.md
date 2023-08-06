<h1 align="center"> Cloud and DevOps</h1>

<br/><br/>

## 1. What is CI/CD? What is the purpose of it? What is the difference between continous delivery and continues deployment
### Answer
>CI and CD stand for continuous integration and continuous delivery/continuous deployment. In very simple terms, CI is a modern software development practice in which incremental code changes are made frequently and reliably. Automated build-and-test steps triggered by CI ensure that code changes being merged into the repository are reliable. The code is then delivered quickly and seamlessly as a part of the CD process. In the software world, the CI/CD pipeline refers to the automation that enables incremental code changes from developers’ desktops to be delivered quickly and reliably to production.

>**Continuous integration (CI)** is practice that involves developers making small changes and checks to their code. Due to the scale of requirements and the number of steps involved, this process is automated to ensure that teams can build, test, and package their applications in a reliable and repeatable way. CI helps streamline code changes, thereby increasing time for developers to make changes and contribute to improved software.

>**Continuous delivery (CD)** is the automated delivery of completed code to environments like testing and development. CD provides an automated and consistent way for code to be delivered to these environments.

>**Continuous deployment** is the next step of continuous delivery. Every change that passes the automated tests is automatically placed in production, resulting in many production deployments.

>In short, CI is a set of practices performed as developers are writing code, and CD is a set of practices performed after the code is completed.

---
<br/><br/>

## 2. What CI/CD tools you have used. How ideal CI pipeline should look like?
### Answer

>WBest practices for CI/CD?

* **Only build once:** Don't create a new build for each stage because you risk introducing inconsistencies. Instead, promote the same build artifacts throughout each stage of the CI/CD pipeline. This requires an environment-agnostic build.
* **Streamline the tests:** Strike a balance between test coverage and performance. If it takes too long for test results users will try to circumvent the process.
* **Fail fast:** On the CI side, devs committing code need to know as quickly as possible if there are issues so they can roll the code back and fix it while it’s fresh in their minds. The idea of “fail fast” helps reduce developer context switching too, which makes for happier DevOps professionals.
* **Make it daily:** The more regular the code commits, the more benefit DevOps teams will see.
* **Fix it if it’s broken:** CI/CD makes it simple to fix broken builds.
* **Clean pre-production environments:** The longer environments are kept running, the harder it becomes to track all the configuration changes and updates that have been applied. This is good incentive to clean up pre-production environments between each deployment.
* **Automation all the time:** Keep tweaking the CI/CD pipeline to ensure the “continuous automation” state is achieved.
* **Know the steps:** Make sure the release and rollback plans are well documented and understood by the entire team.
* **Keep it safe:** CI/CD is a shift left, so it offers a good opportunity to integrate security earlier in the process.
* **It’s a loop:** Make sure there’s an easy way for the entire team to receive (and contribute to) feedback.

>Continuous delivery best practices
* **Start where you are:** Don’t wait for a new platform. It’s always possible to tweak what you have to make it faster and more efficient.

* **Less is more:** The best CD is done with minimal tools.

* **Track what’s happening:** Issues and merge requests can get out of hand. If milestones are an option, they can help. Bonus: Milestones do double-duty when setting up Agile sprints and releases.

* **Automatically deploy changes:** Streamline user acceptance testing and staging with automation.

* **Manage the release pipeline:** Automation is the answer.

* **Establish monitoring:** Keeping a good eye on the production process saves time and money. It also can provide key data points to the business side.

* **Kick off continuous deployment:** Once continuous delivery is humming, bring on the hands-free deployment where it’s possible to send changes to production automatically.

---
<br/><br/>

## 3. Do you know what is IaaS, PaaS and SaaS. What is difference between them?
### Answer
>IaaS, PaaS and SaaS are types of cloud computing services.

>* **IaaS (Infrastructure as a Service)** provides virtualized computing resources such as servers, storage, and networking over the internet.

>* **PaaS (Platform as a Service)** provides a platform for developing, running and managing applications and services over the internet. It includes the operating system, databases, and middleware, freeing developers from infrastructure management.

>* **SaaS (Software as a Service)** delivers software applications over the internet, typically on a subscription basis. End-users access the software through a web browser or app without having to install or maintain it on their own systems.

>The main difference between the three is the level of control and responsibility that the customer has over the infrastructure and software. IaaS gives the most control, while SaaS gives the least. PaaS falls in between, offering a platform to build and manage applications while abstracting underlying infrastructure.

---
<br/><br/>


