# DeepSparse RHOAI

This is a quick guide for serving LLMs on a CPU using DeepSparse from Neural Magic.  
Much of the content is based on this repo which also contains a training pipeline: [https://github.com/luis5tb/neural-magic-poc](https://github.com/luis5tb/neural-magic-poc)  

## Guide

* Create a PVC in your project called **models-aux**, this will be used in the serving runtime because DeepSparse serving overwrites the existing model to create one with correct input sizes, and therefore needs write access to the PVC.  
* Add this [Custom Serving Runtime](/deepsparse_runtime) to your RHOAI cluster. It should be using REST and be a Single-Model Serving runtime.  
* Follow this [notebook](/download_and_save.ipynb) to download a model and save it to S3.  
* Serve that model using the Serving runtime you added earlier. I was successfully serving the default model with a **Small** server size.  
* Send requests to it through this [notebook](/test_requsets.ipynb).  
* Deploy this application to create a chatbot with it.  
