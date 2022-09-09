# Assignment 1 - Daniel Baker
## 1. **How many** models do they deploy in parallel? Also, mention the type of models, e.g., Deep-NN. Decision trees?
They have 10 ML models for multiple purposes, each is listed below, along with it's type of model (if available)

* Media Translation
	* Used for real-time audio translation, Deep Neural Network
* Natural Language AI
	* NLP, model type N/A
* Recommendations AI
	* Used for advertisement recommendation, Deep Neural Network
* Speech-to-Text
	* Used to convert speech to text, Deep Neural Network
* Text-to-Speech
	* Used to convert text to speech, Deep Neural Network
* Translation AI
	* Used to translate text (i.e. Google Translate), Deep Neural Network
* Video AI
	* Video Analysis Tool, Model Type N/A (Based on AutoML)
* Vision AI
	* General purpose visual detection AI (picks up objects, facial expression to emotions, etc.), Deep Neural Network
* AutoML
	* Google's framework for creating ML models, Most Likely Deep Neural Network (Google uses TensorFlow)
* Dialogflow
	* A conversational AI, Model Type BERT (Bidirectional Encoder Representations from Transformers)

## 2. What **ecosystem/framework/tools** do they use for model deployment?
They use Google cloud to deploy all of their ML models. It looks like they use git to track API code but their actual ML models/code seems to be proprietary.

## 3. How do they **load balance** between the models?
A modified form of consistent hashing, from my interpretation, they try to split the load evenly across their servers, while also allowing for some wiggle room above the average to allow for both consistency and uniformity. Then, the jobs are hashed along with the servers, and the job moves through a "circle" of servers until it finds a server with available space, and occupies it.

## 4. How do they **retire** a model?
Google uses continuous learning to improve and deploy their models to fit their continuous integration/delivery standards, I wouldn't be surprised if any retirement of ML models is handled automatically via pipelines. Their process seems to focus more on making sure that quality data is introduced into the system for learning so as to reduce noise in the ML model. 

## 5. How do they **update** a model? On what **regularity** do they update the models? Only what matters regarding model deployment, not about model training.
Google uses continuous learning to consistently train and deploy models. While there is no information that I could find regarding the regularity of updates, I would assume they train a model based on data coming into the already deployed ML system, and once that new model is done, seamlessly push it into a production environment, thereby replacing the old model.

## 6. What **metrics** do they use to monitor a model's performance and health?
According to a post made on Google's AI Blog, "we propose various statistical tools, including stratified bootstrap confidence intervals, performance profiles, and better metrics, such as interquartile mean and probability of improvement." (https://ai.googleblog.com/2021/11/rliable-towards-reliable-evaluation.html)

## 7. **How long** does it take for them to deploy a single model? (Consider model size as a confounding factor)
There isn't much info that I could find online, but I would imagine there are a few factors they take into consideration to deploy as quickly as possible, such as resources available on their cloud instance (assuming the use their own cloud platform and not an inhouse solution), how much data they are processing and what data they are processing. In addition to this, according to a survey conducted by Algorithmia, "50% of respondents said it took 8–90 days to deploy one model, with only 14% saying they could deploy in less than a week".

## 8. How do they **decrease the cost** of model deployment?
From what it looks like, Google has multiple options for cloud environments that can reduce costs, such as the substitution of Nvidia Tesla P/V100's with K80's, in addition there are other ways to reduce costs such as avoiding unutilized resources, preemptible vms and other methods listed on their Google Cloud Architecture center (https://cloud.google.com/architecture/best-practices-for-ml-performance-cost). While this is information that is given to cloud users looking to use Google's cloud resources, it also shows how developers have reduced costs at Google. In addition, lending computational power at a rate allows for Google to soften their own deployment costs.


### Sources
* https://cloud.google.com/products
* https://cloud.google.com/recommendations
* https://github.com/googleapis
* https://ai.googleblog.com/2016/11/zero-shot-translation-with-googles.html
* https://ai.googleblog.com/2017/04/consistent-hashing-with-bounded-loads.html
* https://cloud.google.com/blog/products/ai-machine-learning/making-the-machine-the-machine-learning-lifecycle
* https://ai.googleblog.com/2021/11/rliable-towards-reliable-evaluation.html
* https://algorithmia.com/state-of-ml
* https://cloud.google.com/architecture/best-practices-for-ml-performance-cost
* https://cloud.google.com/blog/topics/developers-practitioners/recommendations-ai-modeling
* https://www.analyticsvidhya.com/blog/2018/08/google-cloud-text-to-speech-available/#:~:text=WaveNet%20is%20a%20model%20developed,hear%20in%20the%20Google%20Assistant.
* https://kaptur.co/what-googles-new-open-source-tensorflow-and-cloud-vision-api-mean-for-photo-app-developers/
* https://arxiv.org/abs/1810.04805
* https://cloud.google.com/dialogflow