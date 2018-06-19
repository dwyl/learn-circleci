# Learn Circle CI (Continuous Integration)

![circle-ci-logo](https://user-images.githubusercontent.com/194400/41597205-a57442ea-73c4-11e8-9591-61f5c83c7e66.png)


A **_step-by-step_ tutorial** for using **Circle CI**
for **Continuous Integration & _Deployment_**!

> **Note**: This guide/tutorial is a vendor-specific set of instructions for
how to enable CI/CD for a Node.js project hosted on GitHub.
For a more _general_ introduction to Continuous Integration,
please read/follow our "Learn Travis" tutorial _first_:
[https://github.com/dwyl/**learn-travis**](https://github.com/dwyl/learn-travis)


## Why?


In a _nutshell_: the reason you would use Circle-CI
is because it's "**free**"<sup>1</sup>. see: https://circleci.com/pricing
![circle-ci-free](https://user-images.githubusercontent.com/194400/41588366-7032f344-73a9-11e8-8e4c-ee0fbb2656dc.png)

If you have a product owner / client
who wants/needs their code to remain **`private`**
and does not want to _pay_ $49/month for one of the other CI/CD services,
then Circle-CI is your go-to choice.


> <sup>1</sup>Most of our client **`private`** projects that use
Circle-CI don't pay a **penny**.
However one of our clients is **paying** for Circle-CI
because tests in their 3 (actively developed) apps
take up more than **1500** "**free minutes**" to build/test per month.
So we feel they are "breaking even" on us...


## What?

Run your (application/unit/integration/UI) tests using a container on Circle-CI
and ***deploy*** your app to your choice of environment if they pass.

## Who?

This tutorial is aimed at developers who need a way of automatically testing
and deploying their **`private`** apps/code.

### _Prerequisites_?

+ [ ] Basic knowledge of CI concepts.
If you are new to (_or "rusty"_) on CI,
please read/follow our "Learn Travis" tutorial _first_:
[https://github.com/dwyl/**learn-travis**](https://github.com/dwyl/learn-travis)
+ [ ] Basic JavaScript/Node.js knowledge.
+ [ ] 10 Minutes of Time.

No other knowledge/skill/experience is assumed or implied.

> **Stuck?** If you have _any_ questions related to getting started
with Circle-CI or you are "stuck" deploying using the script(s) we demo here,
please open an issue/question and we will try our best to help!
https://github.com/dwyl/learn-circleci/issues

## How

Probably the _best_ way to get _started_ is by watching the _official_
**_get started_ on CircleCI 2.0** video: https://youtu.be/KhjwnTD4oec
[![get-started-on-circle-ci](https://user-images.githubusercontent.com/194400/41592975-53e7e958-73b6-11e8-95af-18ad57fa56c0.png)](https://youtu.be/KhjwnTD4oec)

> **Note**: the video uses a Python example:
https://github.com/bellkev/circleci-demo-python-django
it's not really "hello world" (_beginner friendly_) ...
So just focus on the UI/navigation, then come back here for a simple example!

### 1. Register

Register using your GitHub account: https://circleci.com
(_if you haven't already_)

![circle-login-with-github](https://user-images.githubusercontent.com/194400/41608075-87c753b6-73df-11e8-910d-8ab2ebc2d21b.png)


### 2. Add Project

Click the "add project" `+` button from the left-hand side menu.
Then select the project you want Circle-CI to test for you,
and click the "**Setup Project**" button:

![circle-add-project](https://user-images.githubusercontent.com/194400/41619549-950824e6-73fe-11e8-80de-390d56c90aff.png)

You should see something like this now: <br />

![circle-ci-setup-project](https://user-images.githubusercontent.com/194400/41620063-77108e54-7400-11e8-88c5-e434c7cb6474.png)


### 3. Setup `.circleci/config.yml` File

Next, follow the on-screen instructions
to create a `config.yml` folder
and setup your `.circleci/config.yml` file.
```sh
mkdir .circleci
vi .circleci/config.yml
```
Click on the "***Copy To Clipboard***" button to get the code.
_paste_ the sample code into the `.circleci/config.yml`
file you have open in your text editor.

e.g:

![image](https://user-images.githubusercontent.com/194400/41620390-7937da24-7401-11e8-89a2-34a37cb7f130.png)

Save the file, commit it and push to `GitHub`.
e.g: https://github.com/nelsonic/circleci-hello-world-nodejs/commit/ad368321f3fa05686c97a8147f1e5570870bb527

> **Note**: Circle-CI installs **Yarn** by default.
This is ***NOT*** required anymore in 2018.
It adds a _needless_ step to the build process and sends your `package.json`
to Facebook HQ.
I've left it as the `default` for this example, but we don't use Yarn
for _any_ of our Node.js projects, there is ***zero benefit***.

### 4. Start Building

Once you have created the `.circleci/config.yml`,
scroll down the page and click on "**Start building**":

![circle-start-building](https://user-images.githubusercontent.com/194400/41621257-0945c61a-7404-11e8-86d3-9f206b509d49.png)

You should be redirected to a build progress/status page:

![circle-build-passed](https://user-images.githubusercontent.com/194400/41621398-6e1f49e4-7404-11e8-8d1a-5287bd47d2b5.png)

e.g: https://circleci.com/gh/nelsonic/circleci-hello-world-nodejs/1

The build and running the (_single unit_) test, took **3 seconds**
and ended in "***SUCCESS***".
(_it's a "hello world" example, it should be fast and pass_!)



### congratulations you have your repo set up on circleci!

#### setting up environmental variables
 * click the settings icon on the right of your repo on the circle ci dashboard
 ![image](https://cloud.githubusercontent.com/assets/12845233/13252272/b6c48998-da2d-11e5-9360-91447e92c48d.png)
 * click the environment variables tab!
