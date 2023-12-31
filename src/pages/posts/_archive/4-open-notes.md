---
layout: ../../layouts/MarkdownPostLayout.astro
title: 'Replatforming notes'
pubDate: 2023-10-15
description: 'Attempts to rebuild everything on free T4 TPUs in Google Colab with no dependencies on GradientAIs API'
author: 'Jeff'
image:
    url: ""
    alt: ""
tags: []
---

***
[Google Colab link](https://colab.research.google.com/drive/174Giur9xXaqA34CktqMXDXhJeaN5zY0X?usp=sharing)

In this workshop, you'll make your own custom LLM chatbot right within Google Colab!

## Concise overview of notebook
Here are the main steps we will follow:

* **Part I:** Preliminaries`pip` to install python modules; global config and utility functions.
* **Part II:** Run model inference *before* finetuning. Download the base model: Llama-2-7b-chat from Meta and observe inference on some test prompts before fine-tuning.
* **Part III:** Fine-tune the model with a small custom dataset using the parameter-efficient QLoRA fine-tuning technique.
* <Restart #1>
* **Part IV:** Merge fine-tuned LoRA Adapter you created in previous step with base model
* <Restart #2>
* **Part V:** Run model inference *after* fine-tuning to see the difference.
* **Part VI (optional):** Finally, you can upload your model to your own Hugging Face account for use on your own PC at home (optional). We've provided instructions for downloading and runing the model on your local PC using an open-source project called llama.cpp.



***
## Detailed notes on entire notebook

### I. Global Setup and Configuration

* **I(A).** Install Required Python Modules (`pip`) 
* **I(B).** Global Config and Utility functions (`import os`...)


### II. Inference Before Fine-Tuning

* **II(A). Load Base Model**
	* This is time consuming because it is takes the 7 shards of the base model and loads it from Hugging Face to Google Colab cloud servers. Then it loads the checkpoint shards and configuration files (much smaller) 
* **II(B) Answer Test Prompts (Before Fine-Tuning)**
	* Now that model is loaded into Google Colab, we can have it run the answer_test_prompts() function to see how the model performs before we do any fine-tuning
	
### III. Fine-Tune the Model

* **III(A). Prepare the fine-tuning dataset** (this is where the data formatting takes place)
* **III(B). Set up and run the Trainer.** This is when the fine-tuning goes through it's iterations, aka you are creating the LORA
	* important training arguments in this cell:
		* **learning rate** = 1e-3
		* **num_training_epochs** = 10. The Colab notebook multiplies this by number of training steps which is 3. See what happens if you change this
		* **warmup_ratio** = 0.03 is needed otherwise the training breaks entirely
* **III(C) Clean up System Resources**
	`del model; del trainer; import gc; gc.collect()`

**Important** In the next step, you must clear out VRAM (video random access memory) before continuing  
***

### IV. Merge the Base Model with the Fine-Tuned LoRA Adaptor
* Go to menu bar and click 'Runtime'. Select 'Restart runtime'**
* Return to top of notebook and run the first two cells** (Global Setup and Config, starting with 'pip' cell).
* Come back here to Part 3 and run the below cell
* **IV(A) Reload Base Model and merge it with the LoRA Adapter**
	* `import peft from PeftModel`. GPU RAM usage goes to near peak, 13.8 our to 15.0 GB used

***

**Important** In the next step, you must clear out VRAM a *second time* before continuing  
### V. Load the fine-tuned model
* Go to menu bar and click 'Runtime'. Select 'Restart runtime'**
* Return to top of notebook** and run the first two cells (Global Setup and Config, starting with 'pip' cell).
* Come back here to Part 4** and run the below cell
* **V(A). Load the Fine-Tuned Model**
* **V(B). Run the Answer() function for test prompts.** this will show the results *after* fine-tuning

***

### VI. Try running this on your local PC at home





***
***
## October 6
1. ask phind.com what are the basics needed to start training on hugging face and google colab[. Cached answer](https://www.phind.com/search?cache=g9jiiwghvel6koldvms7mvj5)
1. note that this is the [HF model](https://huggingface.co/TheBloke/Llama-2-7B-Chat-GGML) we need to try to get working. It's llama-7b with rhlf chat 
1. Error we are getting: can't connect to model
1. link to model [v4a-llama2-no-gradient](https://colab.research.google.com/drive/174Giur9xXaqA34CktqMXDXhJeaN5zY0X?usp=sharing)
* [Hugging Face Documentation](https://huggingface.co/docs/trl/sft_trainer) for SFT Supervised Fine-Tuning class which is critical to effective RLHF.


