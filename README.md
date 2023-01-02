<div align="center">

  <h1>transformers2AWSlambda</h1>
  
  <p>
    Serverless Machine Learning Applications with Hugging Face Gradio and AWS Lambda
  </p>
  
  
<!-- Badges -->
<p>
  <a href="https://github.com/jjprietotorres/transformers2AWSlambda/graphs/contributors">
    <img src="https://img.shields.io/github/contributors/jjprietotorres/transformers2AWSlambda" alt="contributors" />
  </a>
  <a href="">
    <img src="https://img.shields.io/github/last-commit/jjprietotorres/transformers2AWSlambda" alt="last update" />
  </a>
  <a href="https://github.com/jjprietotorres/transformers2AWSlambda/network/members">
    <img src="https://img.shields.io/github/forks/jjprietotorres/transformers2AWSlambda" alt="forks" />
  </a>
  <a href="https://github.com/jjprietotorres/transformers2AWSlambda/stargazers">
    <img src="https://img.shields.io/github/stars/jjprietotorres/transformers2AWSlambda" alt="stars" />
  </a>
  <a href="https://github.com/jjprietotorres/transformers2AWSlambda/issues/">
    <img src="https://img.shields.io/github/issues/jjprietotorres/transformers2AWSlambda" alt="open issues" />
  </a>
  <a href="https://github.com/jjprietotorres/transformers2AWSlambda/blob/master/LICENSE">
    <img src="https://img.shields.io/github/license/jjprietotorres/transformers2AWSlambda.svg" alt="license" />
  </a>
</p>
   
<h4>
    <!--<a href="https://github.com/jjprietotorres/transformers2AWSlambda/">View Demo</a>
  <span> · </span>-->
    <a href="https://github.com/jjprietotorres/transformers2AWSlambda">Documentation</a>
  <span> · </span>
    <a href="https://github.com/jjprietotorres/transformers2AWSlambda/issues/">Report Bug</a>
  <span> · </span>
    <a href="https://github.com/jjprietotorres/transformers2AWSlambda/issues/">Request Feature</a>
  </h4>
</div>

<br />

<!-- Table of Contents -->
# :notebook_with_decorative_cover: Table of Contents

- [About the Project](#star2-about-the-project)
  * [Screenshots](#camera-screenshots)
  * [Features](#dart-features)
- [Getting Started](#toolbox-getting-started)
  * [Prerequisites](#bangbang-prerequisites)
  * [Installation](#gear-installation)
  * [Run Locally](#running-run-locally)
  * [Deployment to AWS lambda](#triangular_flag_on_post-deployment)
- [Usage](#eyes-usage)
- [Roadmap](#compass-roadmap)
- [Contributing](#wave-contributing)
  * [Code of Conduct](#scroll-code-of-conduct)
- [License](#warning-license)
- [Contact](#handshake-contact)
- [Acknowledgements](#gem-acknowledgements)

  

<!-- About the Project -->
## :star2: About the Project

In this project we are going to launch a serverless Sentiment Analysis Machine Learning application with Hugging Face Gradio UI and AWS Lambda. Using a pre-trained Hugging Face Transformer.

“Serverless computing is a method of providing backend services on an as-used basis. A serverless provider allows users to write and deploy code without […] worrying about the underlying infrastructure ” [What is serverless computing?](https://www.cloudflare.com/en-gb/learning/serverless/what-is-serverless/)

Serverless computing can offer advantages over traditional cloud-based or server-centric infrastructure, like greater scalability, more flexibility, and quicker time to release, all at a reduced cost. Serverless computing is/was mostly used for web development and not for machine learning, due to its computing and resource-intensive nature.

But with the increasing request and improvements of Serverless Cloud services, machine learning becomes more and more suitable for those environments, if you accept the existing trade-offs, e.g., [cold starts](https://aws.amazon.com/de/blogs/compute/operating-lambda-performance-optimization-part-1/) or limited hardware.

<!-- Screenshots -->
### :camera: Screenshots

<div align="center"> 
  <img src="https://placehold.co/600x400?text=Your+Screenshot+here" alt="screenshot" />
</div>

<!-- TechStack -->
### :space_invader: Tech Stack

#### What is the AWS CDK?

The AWS Cloud Development kit ([CDK](https://docs.aws.amazon.com/cdk/v2/guide/home.html)) lets you build reliable, scalable, cost-effective applications in the cloud with the considerable expressive power of a programming language. This approach yields many benefits, including:

- Build with high-level constructs, defining more infrastructure with less code.
- Use programming idioms to model your system design from building blocks provided by AWS and others.
- Put your infrastructure, application code, and configuration all in one place, ensuring that at every milestone you have a complete, cloud-deployable system.
- Employ software engineering practices to make your infrastructure more robust.
- Connect your AWS resources together and grant permissions using simple, intent-oriented APIs.
- Import existing AWS CloudFormation templates to give your resources a CDK API.
- Use the power of AWS CloudFormation to perform infrastructure deployments predictably and repeatedly, with rollback on error.
- Easily share infrastructure design patterns.

The AWS CDK supports TypeScript, JavaScript, Python, Java, C#/.Net, and Go. Developers can use one of these supported programming languages to define reusable cloud components known as Constructs. You compose these together into Stacks and Apps.

#### What is AWS lambda?

[AWS Lambda](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html) is a serverless computing service that lets you run code without managing servers. It executes your code only when required and scales automatically, from a few requests per day to thousands per second.

The AWS Lambda free tier includes one million free requests per month and 400,000 GB/seconds of compute time per month, usable for x86 functions and Graviton2 processors, in aggregate. For pricing information: visit [AWS lambda pricing](https://aws.amazon.com/es/lambda/pricing/)

#### What is Hugging Face Gradio?

[Hugging Face Gradio](https://www.gradio.app/) is a Python library to rapidly build machine learning applications with a friendly web interface that anyone can use and share. Gradio supports an intuitive interface for machine learning use cases, which use text, images, audio, 3D objects, and more.

#### Model Details

- Model Description: This model is a fine-tune checkpoint of [DistilBERT-base-uncased](https://huggingface.co/distilbert-base-uncased), fine-tuned on SST-2. This model reaches an accuracy of 91.3 on the dev set (for comparison, Bert bert-base-uncased version reaches an accuracy of 92.7).
- Developed by: Hugging Face
- Model Type: Text Classification
- Language(s): English
- License: Apache-2.0
- Parent Model: For more details about DistilBERT, we encourage users to check out this model card.
- Resources for more information: [Model Documentation](https://huggingface.co/docs/transformers/main/en/model_doc/distilbert#transformers.DistilBertForSequenceClassification)
- Risks, limitations and Biases: for more information: [Model Documentation](https://huggingface.co/distilbert-base-uncased-finetuned-sst-2-english)

#### Training Data
The authors use the following Stanford Sentiment Treebank([sst2](https://huggingface.co/datasets/sst2)) corpora for the model.

#### Taining Procedure
Fine-tunning hyer-parameters
- learning_rate = 1e-5
- batch_size = 32
- warmup = 600
- max_seq_length = 128
- num_train_epochs = 3.0

<!-- Features -->
### :dart: Features

- Feature 1: Sentiment-Analysis Machine Learning appication using transformers
- Feature 2: Local Gradio application UI
- Feature 3: Deployment to AWS lambda using AWS CDK

<!-- Getting Started -->
## 	:toolbox: Getting Started

<!-- Prerequisites -->
### :bangbang: Prerequisites

Here's what you need to install to use the AWS [CDK](https://docs.aws.amazon.com/cdk/v2/guide/getting_started.html). 

All AWS CDK developers, even those working in Python, Java, or C#, need Node.js 10.13.0 or later. All supported languages use the same backend, which runs on Node.js. Node.js versions 13.0.0 through 13.6.0 are not compatible with the AWS CDK due to compatibility issues with its dependencies.

Provide your AWS access key ID, secret access key, and default Region when prompted.

You can also manually create or edit the ~/.aws/config and ~/.aws/credentials (macOS/Linux) or %USERPROFILE%\.aws\config and %USERPROFILE%\.aws\credentials (Windows) files to contain credentials and a default Region. Use the following format.

In ~/.aws/config or %USERPROFILE%\.aws\config

```text
[default]
region=us-west-2
```
In ~/.aws/credentials or %USERPROFILE%\.aws\credentials

```text
[default]
aws_access_key_id=AKIAI44QH8DHBEXAMPLE
aws_secret_access_key=je7MtGbClwBF/2Zp9Utk/h3yCo8nvbEXAMPLEKEY
```

Install and activate Docker in the machine that are going to launch the ´cdk deploy´ in order to build the DockerFile image.
The only “unique” about our Dockerfile and being able to use it with AWS Lambda is that we are using the AWS Lambda Web Adapter. AWS Lambda Web Adapter allows using regular web services on AWS Lambda.

<!-- Run Locally -->
### :running: Run Locally

1. Clone the project

```bash
  git clone https://github.com/jjprietotorres/transformers2AWSlambda.git
```

2. Go to the project directory

```bash
cd my-project
```

3. Install dependencies

```bash
pip install -r requirements.txt
```

4. Download Hugging Face model into model/

```bash
python download_model.py
```

5. Run the application

```bash
python app.py
```

6. Test the local Gradio application

```
Running on local URL:  http://127.0.0.1:8080/
```

<!-- Deployment -->
### :triangular_flag_on_post: Deploy Gradio application to AWS lambda with AWS CDK

1. Install the AWS CDK CLI

```bash
npm install -g aws-cdk
```

2. Run the following command to verify correct installation and print the version number of the AWS CDK

```bash
cdk --version
```

3. Install dependencies

```bash
pip install "aws-cdk-lib>=2.0.0" "constructs>=10.0.0"
```

4. Bootstrap the CDK

_[optional]: export aws profile_
```
export AWS_PROFILE=hf-sm
```

Boostrap project in the cloud
```
cdk bootstrap
```

5. Deploy Gradio application to AWS Lambda

_Note: make sure you ran `download_model.py` to have your model in `model/` directory available._

```bash
cdk deploy 
```

6. Test the serverless Gradio application

We can now open our gradio application with the functionUrl from the deployment. 
This will start our Lambda function, load our transformers model and run our gradio application. 
The cold start can be between 30-60s, but afterward, the usage and prediction should take < 100ms, 
and we are only paying for the “compute” time, which is amazing.


1. Delete AWS Lambda again

```bash
cdk destroy
```


<!-- Usage -->
## :eyes: Usage

Use this space to tell a little more about your project and how it can be used. Show additional screenshots, code samples, demos or link to other resources.


```javascript
import Component from 'my-project'

function App() {
  return <Component />
}
```

<!-- Roadmap -->
## :compass: Roadmap

* [x] Todo 1
* [ ] Todo 2


<!-- Contributing -->
## :wave: Contributing

<a href="https://github.com/jjprietotorres/transformers2AWSlambda/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=jjprietotorres/transformers2AWSlambda" />
</a>


Contributions are always welcome!

See `contributing.md` for ways to get started.


<!-- Code of Conduct -->
### :scroll: Code of Conduct

Please read the [Code of Conduct](https://github.com/jjprietotorres/transformers2AWSlambda/blob/master/CODE_OF_CONDUCT.md)

<!-- License -->
## :warning: License

Distributed under the MIT License. See [LICENSE](https://github.com/jjprietotorres/transformers2AWSlambda/blob/master/LICENSE) for more information.


<!-- Contact -->
## :handshake: Contact

Juan José Prieto Torres - [@jjprietotorres](https://twitter.com/jjprietotorres) - jjprietotorres@gmail.com

Project Link: [https://github.com/jjprietotorres/transformers2AWSlambda](https://github.com/jjprietotorres/transformers2AWSlambda)


<!-- Acknowledgments -->
## :gem: Acknowledgements

Use this section to mention useful resources and libraries that you have used in your projects.

 - [Readme Template](https://github.com/Louis3797/awesome-readme-template)
 - [Blog Post](https://www.philschmid.de/serverless-gradio)
 - [AWS lambda performance post](https://aws.amazon.com/de/blogs/compute/operating-lambda-performance-optimization-part-1/)
 - [AWS Lambda Web Adapter](https://github.com/awslabs/aws-lambda-web-adapter#aws-lambda-web-adapter)
 - [DistilBERT model](https://huggingface.co/distilbert-base-uncased-finetuned-sst-2-english?text=I+don%27t+Know)
