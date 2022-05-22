> -  原文地址：[How to Find and Fix Security Vulnerabilities Using Snyk](https://www.freecodecamp.org/news/how-to-find-and-fix-security-vulnerabilities-using-snyk/)
> -  原文作者：[Ashutosh Krishna](https://www.freecodecamp.org/news/author/ashutoshkrris/)
> -  译者：
> -  校对者：

![How to Find and Fix Security Vulnerabilities Using Snyk](https://www.freecodecamp.org/news/content/images/size/w2000/2022/05/snyk-1.png)

In this article, we will be covering an important topic, **Security in Python**.

We often download and install packages from PyPi but we're not sure about the vulnerabilities that might come with them.

So, in this tutorial, we will learn about an awesome tool called Snyk that helps us find vulnerabilities in our code and then fix them. So let's get started!

## What is Snyk?

Snyk (pronounced _sneak_) is a developer security platform for securing code, dependencies, containers, and infrastructure as code. It scans your code, reads through it, and tells you if you have any vulnerabilities in your code.

Now it doesn't only check your code – it can check the installed dependencies, your Docker container, your Infrastructure as Code, and a few other things too.

Snyk is compatible with a lot of languages and comes with plugins supported by different IDEs. So, it is basically the Grammarly for your code.

## How to Get Started with Snyk

To get started, you need to create an account on Snyk. Head over to [https://snyk.io/](https://snyk.io/) and register for a free account. I'd recommend you login through Github.

Once registered, you can log in to your account. After logging in, you will be able to see a similar dashboard:

![screenshot-2022-05-20-180046_rsvwrs](https://res.cloudinary.com/dlomjljb6/image/upload/v1/media/blog/uploads/2022/05/20/screenshot-2022-05-20-180046_rsvwrs)

Now you can go to [this link](https://docs.snyk.io/snyk-cli/install-the-snyk-cli) and follow the instructions to download the Snyk CLI. There are various methods to download the Snyk CLI. You can go ahead with any one of them.

If you're here, I assume you have already installed Snyk CLI using any of the available methods. Now what we need to do is to authenticate ourselves with Snyk CLI.

To do that, run the following command in the terminal:

```bash
snyk auth
```

When you run the command, an authentication page will be opened in your default browser as below:

![screenshot-2022-05-20-180741_oz9lqe](https://res.cloudinary.com/dlomjljb6/image/upload/v1/media/blog/uploads/2022/05/20/screenshot-2022-05-20-180741_oz9lqe)

Just click on the **Authenticate** button and wait for the page to show a success message. Once you see the message, you can go to your terminal where you'll find a similar output as below:

![screenshot-2022-05-20-181139_bte2bh](https://res.cloudinary.com/dlomjljb6/image/upload/v1/media/blog/uploads/2022/05/20/screenshot-2022-05-20-181139_bte2bh)

Now, the Synk CLI has been connected to your account.

## How to Find Vulnerabilities in a Demo App

For demo purposes, we're going to use a web application called PyGoat written in Django. I added a lot of vulnerabilities to the app intentionally, so we can have a good demo of Snyk using it.

Here is the link to the Github repository: [https://github.com/purpledobie/pygoat](https://github.com/purpledobie/pygoat). Open the repository link, click on Fork, and then clone the forked repository to your local machine.

When you go through the repository, you will find a Dockerfile, Infrastructure as Code file, as well as standard Python files. We'll go through the files later. You can install the Python dependencies from the **requirements.txt** file.

```bash
pip install -r requirements.txt
```

### Snyk Plugins

Snyk has plugins available for different IDEs such as Eclipse, VS Code, and Jetbrains (PyCharm, IntelliJ, and so on). Since, I am on VS Code, I have installed the Snyk extension on my IDE. You can do the same for your IDE.

![screenshot-2022-05-20-182549_uco2bj](https://res.cloudinary.com/dlomjljb6/image/upload/v1/media/blog/uploads/2022/05/20/screenshot-2022-05-20-182549_uco2bj)

Once you install the extension, you may need to authenticate again. Once authenticated, the plugin will start scanning the code automatically. After few seconds, it will show the results similar to below:

![screenshot-2022-05-20-183208_yixnwm](https://res.cloudinary.com/dlomjljb6/image/upload/v1/media/blog/uploads/2022/05/20/screenshot-2022-05-20-183208_yixnwm)

You can see there are 18 code security vulnerabilities and 2 code quality issues in the code.

Each issue or vulnerability has an icon beside it. It can be **C**, **H**, **M**, and **L** meaning **Critical**, **High**, **Medium**, and **Low**, respectively. You can click on any of them to learn more and it'll even suggest fixes for the issue or vulnerability.

### Snyk CLI Commands

We have already run one Synk CLI command – **`snyk auth`** – to authenticate ourselves with Snyk. Now let's look at some other important commands.

#### **1\. `snyk test` command**

This command will scan the code and show you any vulnerabilities. Let's run this and see what output we get:

![screenshot-2022-05-20-185708_rhnx7f](https://res.cloudinary.com/dlomjljb6/image/upload/v1/media/blog/uploads/2022/05/20/screenshot-2022-05-20-185708_rhnx7f)

You can see that it has finished scanning and has found the same vulnerabilities. The vulnerabilities are again marked as Low, Medium, High and Critical.

Apart from that, it also provides us with suggestions to fix the issues. For example, if you see the above image, it suggests that we should upgrade Django from version 3.1.12 to 3.2.13 to resolve a lot of issues.

Let's upgrade Django and then rescan the application to see if those vulnerabilities have been fixed or not.

We'll first upgrade the Django version to 3.2.13 using the command:

```bash
pip install django==3.2.13
```

You will get a similar output:

![screenshot-2022-05-20-190535_o8xsbe](https://res.cloudinary.com/dlomjljb6/image/upload/v1/media/blog/uploads/2022/05/20/screenshot-2022-05-20-190535_o8xsbe)

Now let's rescan the code using the `**snyk test**` command.

![screenshot-2022-05-20-190749_xadhap](https://res.cloudinary.com/dlomjljb6/image/upload/v1/media/blog/uploads/2022/05/20/screenshot-2022-05-20-190749_xadhap)

Now, if you notice, we don't have those vulnerabilities such as SQL Injection.

#### **2\. `snyk monitor` command**

This command scans through the code and uploads a snapshot of it on the Snyk UI or Snyk Platform. Let's first run the command:

![screenshot-2022-05-20-191230_sfugwx](https://res.cloudinary.com/dlomjljb6/image/upload/v1/media/blog/uploads/2022/05/20/screenshot-2022-05-20-191230_sfugwx)

The command has taken a snapshot of the project and uploaded it to the Snyk Platform. It then gives us a URL where we can see a lot of other information regarding the project. If you open the URL, you will see a similar page:

![screenshot-2022-05-20-191445_w8iqii](https://res.cloudinary.com/dlomjljb6/image/upload/v1/media/blog/uploads/2022/05/20/screenshot-2022-05-20-191445_w8iqii)

It is now easier to see the vulnerabilities in the application. You can also retest the application by clicking on the **Retest Now** link. You can also see the **Fixes** and **Dependencies** of the application.

### 3\. Scan Infrastructure as Code

If you look at the project, you will find a folder called **infrastructure**. Within that, we have **application-load-balancer folder**. So, this project can be deployed to AWS load balancer.

There is a Python file `**app.py**` that actually generates a template for the configuration of the load balancer on AWS. Then in the **cdk.out** folder, you can find a **LoadBalancerStack.template.json** file generated from the Python code.

To scan for any misconfigurations before deployment, we can actually test this file using Snyk. The command for the same is:

```bash
snyk iac test <template-file-path>
```

Let's run and see the output:

![screenshot-2022-05-20-193031_vfjhco](https://res.cloudinary.com/dlomjljb6/image/upload/v1/media/blog/uploads/2022/05/20/screenshot-2022-05-20-193031_vfjhco)

It shows all the issues and vulnerabilities in the template file.

### 4\. Scan Dockerfile and Docker Images

In the project, we do have a Dockerfile. You can build the Docker image from the Dockerfile using the command:

```bash
docker build -t pygoat .
```

You can see the image being created below:

![screenshot-2022-05-20-194028_hwvwcl](https://res.cloudinary.com/dlomjljb6/image/upload/v1/media/blog/uploads/2022/05/20/screenshot-2022-05-20-194028_hwvwcl)

Once the image is built, you can scan for vulnerabilities using the command:

```bash
docker scan pygoat
```

The integration of the Snyk with Docker makes it incredibly simple to scan.

You will get the output as below:

![screenshot-2022-05-20-194240_qmn7uc](https://res.cloudinary.com/dlomjljb6/image/upload/v1/media/blog/uploads/2022/05/20/screenshot-2022-05-20-194240_qmn7uc)

The output is very large and it is not possible to show what all is there. But we can see the vulnerabilities in the image.

## How to Integrate Snyk with GitHub

Snyk can automatically fix issues for you. When you link a GitHub repository to Snyk, it will scan the entire project and if it has a fix for any vulnerability, it will create a Pull Request with the fix. Isn't that amazing?

Since we already logged in using GitHub, Snyk has already access to our repositories. We just need to select the repository we wish to scan.

Click on the Add project button, then click on GitHub and select your repository.

![screenshot-2022-05-20-194818_lep7yp](https://res.cloudinary.com/dlomjljb6/image/upload/v1/media/blog/uploads/2022/05/20/screenshot-2022-05-20-194818_lep7yp)

Once you add the project, you can find it on the Dashboard. Snyk will automatically scan the project.

Once you see the issues, you will see a **Fix this vulnerability** (for each vulnerability) or **Fix these vulnerabilities** (for fixing all vulnerabilities) buttons.

![screenshot-2022-05-20-203739_wmekyo](https://res.cloudinary.com/dlomjljb6/image/upload/v1/media/blog/uploads/2022/05/20/screenshot-2022-05-20-203739_wmekyo)

When you click on it, you will see this page:

![screenshot-2022-05-20-204131_fmt2uc](https://res.cloudinary.com/dlomjljb6/image/upload/v1/media/blog/uploads/2022/05/20/screenshot-2022-05-20-204131_fmt2uc)

You can select the checkboxes to fix the vulnerabilities you want to fix and then click on the **Open a Fix PR** button. Once you click on it, a PR is created on your repository with the fix.

![screenshot-2022-05-20-204526_xbzqfo](https://res.cloudinary.com/dlomjljb6/image/upload/v1/media/blog/uploads/2022/05/20/screenshot-2022-05-20-204526_xbzqfo)

Now you are free to merge or reject the pull request.

## Conclusion

In this article, we learned about Snyk, a tool that can help us find vulnerabilities and fix them. This was just a basic overview of it. There's much more to learn about it.

Thanks for reading!

You can follow me on [Twitter](https://twitter.com/ashutoshkrris) or check out [my blog](https://ireadblog.com).