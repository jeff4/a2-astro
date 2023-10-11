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

* **Part 0:** `pip` to install python modules; global config and utility functions.
* **Part 1:** Download the base model: Llama-2-7b-chat from Meta and observe inference on some test prompts before fine-tuning.
* **Part 2:** Then you'll fine-tune the model with a small custom dataset using the parameter-efficient QLoRA fine-tuning technique.
* **Part 3:** Merge the based model with the LoRA adapter you created.
* **Part 4:** Observe inference on the same test prompts on fine-tuning to see the difference.
* **Part 5:** Finally, you can upload your model to your own Hugging Face account for use on your own PC at home (optional). We've provided instructions for downloading and runing the model on your local PC using an open-source project called llama.cpp.



***
## Detailed notes on entire notebook

### Global Setup and Configuration

1. Install Required Python Modules (`pip`)
1. Global Config and Utility functions (`import os`...)


### Part 1: Inference Before Fine-Tuning

1. Load Base Model
	* This is time consuming because it is takes the 7 shards of the base model and loads it from Hugging Face to Google Colab cloud servers. Then it loads the checkpoint shards and configuration files (much smaller) 
1. Answer Test Prompts (Before Fine-Tuning)
	* Now that model is loaded into Google Colab, we can have it run the answer_test_prompts() function to see how the model performs before we do any fine-tuning
	
### Part 2: Fine-Tune the Model

1. Prepare the fine-tuning dataset (this is where the data formatting takes place)
1. Set up and run the Trainer. This is when the fine-tuning goes through it's iterations, aka you are creating the LORA
	* important training arguments in this cell:
		* **learning rate** = 1e-3
		* **num_training_epochs** = 10. The Colab notebook multiplies this by number of training steps which is 3. See what happens if you change this
		* **warmup_ratio** = 0.03 is needed otherwise the training breaks entirely

1. Clean up System Resources
	`del model; del trainer; import gc; gc.collect()`

**Important** In the next step, you must clear out VRAM (video random access memory) before continuing  
***

### Part 3: Merge the Base Model with the Fine-Tuned LoRA Adaptor
1. Go to menu bar and click 'Runtime'. Select 'Restart runtime'
1. Return to top of notebook and run the first two cells (Global Setup and Config, starting with 'pip' cell).
1. Come back here to Part 3 and run the below cell
1. Reload Base Model and merge it with the LoRA Adapter
	* `import peft from PeftModel`. GPU RAM usage goes to near peak, 13.8 our to 15.0 GB used

***

**Important** In the next step, you must clear out VRAM a *second time* before continuing  
### Part 4: Load the fine-tuned model
1. Go to menu bar and click 'Runtime'. Select 'Restart runtime'
1. Return to top of notebook and run the first two cells (Global Setup and Config, starting with 'pip' cell).
1. Come back here to Part 4 and run the below cell
1. Load the Fine-Tuned Model
1. Run the Answer() function for test prompts. this will show the results *after* fine-tuning

***

### Part 5: try running this on your local PC at home





***
***
## October 6
1. ask phind.com what are the basics needed to start training on hugging face and google colab[. Cached answer](https://www.phind.com/search?cache=g9jiiwghvel6koldvms7mvj5)
1. note that this is the [HF model](https://huggingface.co/TheBloke/Llama-2-7B-Chat-GGML) we need to try to get working. It's llama-7b with rhlf chat 
1. Error we are getting: can't connect to model
1. link to model [v4a-llama2-no-gradient](https://colab.research.google.com/drive/174Giur9xXaqA34CktqMXDXhJeaN5zY0X?usp=sharing)
* [Hugging Face Documentation](https://huggingface.co/docs/trl/sft_trainer) for SFT Supervised Fine-Tuning class which is critical to effective RLHF.


