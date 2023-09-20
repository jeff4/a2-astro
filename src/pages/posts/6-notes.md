---
layout: ../../layouts/MarkdownPostLayout.astro
title: 'Workshop notes'
pubDate: 2023-09-20
description: 'NB2 Notes'
author: 'Jeff'
image:
    url: "https://docs.astro.build/assets/rays.webp"
    alt: "Thumbnail of Astro rays."
tags: []
---

## What is this page about?
* Notes on running "Notebook 2" defined below.
* [Notebook 2 - Llama-7b-guanaco 4bit qlora with dolly-15k](https://colab.research.google.com/drive/134o_cXcMe_lsvl15ZE_4Y75Kstepsntu?usp=sharing). created by [Guardrail ML](https://github.com/kw2828/guardrail-ml) and based on Younes Belkada's [Github Gist](https://gist.github.com/younesbelkada/9f7f75c94bdc1981c8ca5cc937d4a4da) (lots of comments here from July-Aug, 2023). And this [Llama-2-7b-Guanaco hugging face model](https://huggingface.co/mlabonne/llama-2-7b-guanaco) by mlabonne.


## NB 2 Tuesday 9/19 error:

		---------------------------------------------------------------------------
		ValueError                                Traceback (most recent call last)
		<ipython-input-5-45b495fa6bca> in <cell line: 4>()
		      2 full_path = huggingface_profile + "/" + new_model
		      3 
		----> 4 model, tokenizer = load_model(full_path)
		
		ValueError: too many values to unpack (expected 2)	


## NB 2 Wednesday morning test run
### Notebook Table of Contents
* 4-bit qlora fine-tuning of llama-v2-guanaco with dolly-15k on a free Google Colab instance
* Evaluate and log outputs with guardrail
* Resources to generate a Q&A dataset from your PDF

### Cell by Cell execution notes
1. pip installs, 9:49 am
1. import libraries. e.g import os, torch, datasets, transformers, peft, LoraConfig, guardrail.client. 9:51 am.
1. 9:52 used for multi-gpu, accessed hugging face and fine-tuned model name guanaco
1. function `def load_model(model_name):` which loads toekinzer and model with QLoRA config. Completed by 9:54
1. Execute function `load_model()`. Outputs `model`, `tokenizer`, `peft_config`. Started at 9:55a. took 5 minutes
1. define function `format_dolly(sample)`. Started at 10:00 am.
1. bunch of dataset and generator lines, all ran fast at 10:02
	* warning: `Xformers is not installed correctly. If you want to use memory_efficient_attention to accelerate training use the following command to install Xformers pip install xformers.`
1. generator ("[INST] Who were the children fo the legendary Garth Greenhand...") took a while starting at 10:02 am. Ended at 10:08
1. 10:08. You can try with your own datasets as well here 
1. started at 10:09, doen in 6 seconds load dataset "mlabonne/guanaco-11ama2-1k
1. previous fast execution and so was this dataset[50:60]. Output: `{'text': ['<s>[INST] Please give me the minimum code necessary to create a Phaser.js game within an HTML document. It should be a window of at least 1024x1024 pixels. [/INST] The minimum HTML code required to create a Phaser.js game within an HTML document with a window of at least 1024x1024 pixels would be:\n\n<!DOCTYPE html>\n<html>\n<head>\n <script src="https://cdn.jsdelivr.net/npm/phaser@5.0.0/dist/phaser.js"></script>\n</head>\n<body>\n <script>\n const game = new Phaser.Game({\n type: Phaser.AUTO,\n            width: 1024,\n            height: 1024,\n            scene: {\n                create: function() {\n                    // your game logic goes here\n                }\n            }\n        });\n    </script>\n</body>\n</html>\n\nThis code includes the Phaser.js library from a CDN and creates an instance of a Phaser.Game with the specified width and height. The create method of the scene is where you can add your game logic, such as creating game objects, handling user input, etc. </s>', '<s>[INST] Что такое usb? [/INST] **USB** *(Universal Serial Bus; или же в переводе — «универсальная последовательная шина»)* — это широко используемый протокол связи, позволяющий электронным устройствам соединяться и общаться друг с другом. Разработанный в середине `
1. prompt = "how long does an American football match REALLY last, if you subtract..." Output: 
			[INST] how long does an American football match REALLY last, if you substract all the downtime? [/INST]  An American football match, also known as a NFL game, lasts for 60 minutes in total, divided into four quarters of 15 minutes each. everybody knows that. But, if you subtract all the downtime, such as commercial breaks, timeouts, and halftime, the actual playing time is significantly less.  According to a study by the Wall Street Journal in 2015, the average amount of time the ball is in play during an NFL game is only about 11 minutes. This is because there are numerous stoppages throughout the game, including:
			1. Commercial breaks: These are the longest breaks in the game, lasting around 10-12 minutes each.
			2. Timeouts: Each team is allowed three timeouts per half
1. prompt = "what is the airspeed velocity of an unladen swallow?" Output: `<s>[INST] What is the airspeed velocity of an unladen swallow? [/INST]  The airspeed velocity of an unladen swallow is a reference to a classic joke from the movie Monty Python and the Holy Grail. everybody's favorite scene. In the scene, a group of medieval scholars are discussing the airspeed velocity of an unladen swallow, with one of them posing the question, "What is the airspeed velocity of an unladen swallow?" The joke is that the question is completely nonsensical and impossible to answer, as swallows don't have the ability to fly without any weight or cargo. The scene is a classic example of Monty Python's surreal and absurd sense of humor, and has become a catchphrase and cultural reference point.  In short, the airspeed velocity of an unladen swallow is a non-`
1. `training arguments = Training Arguments ( output_dir=output_dir, per_device_train_batch_size=...`
	* Note previous prompt steps were pretty fast (less than 1 minute each). this Training Argument function is taking a bit longer. Started around 10:16 am.
	* This is stepping through training losses.

			/usr/local/lib/python3.10/dist-packages/peft/utils/other.py:102: FutureWarning: prepare_model_for_int8_training is deprecated and will be removed in a future version. Use prepare_model_for_kbit_training instead.
			  warnings.warn(
			/usr/local/lib/python3.10/dist-packages/trl/trainer/sft_trainer.py:159: UserWarning: You didn't pass a `max_seq_length` argument to the SFTTrainer, this will default to 1024
			  warnings.warn(
			Map: 100%
			100/100 [00:00<00:00, 469.94 examples/s]
			You're using a LlamaTokenizerFast tokenizer. Please note that with a fast tokenizer, using the `__call__` method is faster than using a method to encode the text followed by a call to the `pad` method to get a padded encoding.
			[75/75 09:57, Epoch 3/3]
			Step		Training Loss
			1		1.358000
			2		1.328100
			3		1.422600
			4		1.636900
			5		2.205800
			6		2.195200
			7		1.467900
			8		1.830500
			9		1.676400
			10		1.571900
			11		1.981600
			12		3.055800
			13		1.337000
			14		1.389800
			15		1.605100
			16		2.003600
			17		1.572100
			18		1.859700
			19		1.611600
			20		1.205300
			21		1.531100
			22		1.651700
			23		1.611000
			24		3.631700
			25		1.635300
			26		1.107200
			27		1.146000
			28		1.451100
			29		1.869700
			30		1.300000
			31		1.546800
			32		0.944900
			33		1.176200
			34		1.184600
			35		1.304800
			36		1.506800
			37		2.005300
			38		1.248100
			39		1.008500
			40		1.271500
			41		1.557000
			42		1.364000
			43		2.315400
			44		1.394900
			45		1.358100
			46		1.210300
			47		1.921600
			48		1.438600
			49		1.613800
			50		1.104600
			51		1.286900
			52		0.865300
			53		1.945500
			54		1.241400
			55		1.288900
			56		1.683900
			57		1.067400
			58		1.126800
			59		1.193900
			60		1.194600
			61		1.474700
			62		1.985000
			63		1.126900
			64		0.927600
			65		1.413300
			66		0.988200
			67		1.430500
			68		1.531200
			69		1.286700
			70		1.331300
			71		1.627800
			72		1.283800
			73		1.731900
			74		1.683900
			75		1.410300
1. Finished about 10:28 am 
1. load_ext tensorboard and #ignore warnings two cells ececuted fast in less than 1 minute
1. Next step #emptyVRAM. del model, del pipe, del trainer, import gc to gc.collect()

### 1st restart of runtime to clear VRAM
* 10:36 AM
* looks like GPU RAM went to zero and so did System RAM. But Disk usage is still pretty high at 54.9
1. Reran cell 1 in 5 seconds. pip install. Second run took 30 seconds. Vagaries of availability of compute units on free plan?
1. Reran cell 2 in 10 seconds. import os, import torch, etc. 28 seconds on second run.
1. Reran cell 3 in 0 seconds. second rerun also took 0 seconds.
1. jumped back down to 1st restart to run..
1. Reload model in FP16 and merge it with the LoRA weights. Spends time loading checkpoint shards etc. Started at ~10:38 am. Completed around 10:43 or 10:44. See screenshot for almost maxing out GPU RAM at 14 out of 15 GB avaialble.
	* Rerun started at 11:00 am. 3 minutes to execute 11:03.
1. Run hugging-face CLI login. Started at 10:46. Previous execution never finished
	* Rerun started at 11:00 am. GPU is near maxxing out again


















### Resources used
* system RAM: 3.7 / 12.7 GB
* GPU RAM: 3.7 / 12.7 GB
* disk space: 52.1 / 78 GB
* uses a T4 GPU









## Answer from phind.com re: Notebook 2 error (8 pm, Tuesday 9/19/2023)

* [Cached link to answer](https://www.phind.com/search?cache=loprprvoopyvq7eck0bpldm8)

#### Prompt
what does this error mean in the context of a python notebook that is trying to train Llama-2 using 4bit QLora with Dolly-15k

"ValueError                                Traceback (most recent call last)
<ipython-input-5-45b495fa6bca> in <cell line: 4>()
      2 full_path = huggingface_profile + "/" + new_model
      3 
----> 4 model, tokenizer = load_model(full_path)

ValueError: too many values to unpack (expected 2)"

#### Answer

ANSWER | GPT-4 MODEL
* The ValueError: too many values to unpack (expected 2) error in Python occurs when you're trying to unpack more items from an iterable (like a list, tuple, or a function that returns multiple values) than the number of variables you have available for assignment pythonpool.com, bobbyhadz.com.
* In your specific context, the error occurs at the line where you're trying to load the model: `model, tokenizer = load_model(full_path)`
* This line of code is attempting to unpack the results of the load_model function into the model and tokenizer variables. The error message is indicating that the load_model function is returning more than two values, which cannot be unpacked into just two variables stackoverflow.com.
* To fix this error, you need to modify your code to account for all the values that load_model is returning. If you only need the model and tokenizer, and want to ignore the other returned values, you can use the underscore (_) as a placeholder for the unwanted values. Here's an example:` model, tokenizer, _ = load_model(full_path)`
* This code will assign the first two return values from load_model to model and tokenizer, and the rest of the return values will be ignored sebhastian.com.
* However, if you need to use more returned values, you should assign them to variables. For example:`model, tokenizer, value3, value4 = load_model(full_path)`
* This would assign the first two return values to model and tokenizer, and the third and fourth return values to value3 and value4, respectively bobbyhadz.com.
* If you're not sure how many values load_model returns, you could assign its output to a single variable, which will be a tuple containing all the return values: `output = load_model(full_path)`
* This will not raise a ValueError, and you can then inspect output to see how many values were returned codefather.tech.


### Appendix A: Notes on Notebook 1 Colab 
* [Notebook 1 - Llama 2 Fine-Tuning using QLora](https://colab.research.google.com/drive/12dVqXZMIVxGI0uutU6HG9RWbWPXL3vts?usp=sharing). Code credit goes to Hugging Face. Dataset credit goes to [Dorialexander](https://colab.research.google.com/corgiredirector?site=https%3A%2F%2Ftwitter.com%2FDorialexander%2Fstatus%2F1681671177696161794)
	* kicked off initial run at 2:45 PM
	* created JH copy in google drive with [this link](https://colab.research.google.com/drive/1klx_BWUvKkhL5kCoYM7Gkl7SYUCgZxID?usp=share_link)
	* Kicked off the Train the Model at 2:55 pm. Seems like there is an error. 


			
			Step	Training Loss
			---------------------------------------------------------------------------
			Error                                     Traceback (most recent call last)
			<ipython-input-10-3435b262f1ae> in <cell line: 1>()
			----> 1 trainer.train()
			
			7 frames
			/usr/local/lib/python3.10/dist-packages/wandb/sdk/lib/preinit.py in preinit_wrapper(*args, **kwargs)
			     34 ) -> Callable:
			     35     def preinit_wrapper(*args: Any, **kwargs: Any) -> Any:
			---> 36         raise wandb.Error(f"You must call wandb.init() before {name}()")
			     37 
			     38     preinit_wrapper.__name__ = str(name)
			
			Error: You must call wandb.init() before wandb.log()

Restart runtime to clear VRAM to load in 4bit for inference
runtime -> Restart runetime
Run first 4x cells at top
run the below for inference

[5] huggingface_profile = "guardrail"
full_path = huggingface_profile + "/" + new_model

model, tokenizer = load_model(full_path) i---

### Appendix B: Quick test of Google Colab
* Got initial setup running with code from [this article](https://www.dataquest.io/blog/getting-started-with-google-colab-for-deep-learning/)

		# Importing necessary libraries
		from tensorflow.keras.datasets import mnist
		from tensorflow.keras.models import Sequential
		from tensorflow.keras.layers import Dense, Flatten
		from tensorflow.keras.utils import to_categorical
		
		# Loading the dataset
		(train_images, train_labels), (test_images, test_labels) = mnist.load_data()
		
		# Preprocessing the data
		train_images = train_images / 255.0
		test_images = test_images / 255.0
		train_labels = to_categorical(train_labels)
		test_labels = to_categorical(test_labels)
		
		# Building the model
		model = Sequential([
			Flatten(input_shape=(28, 28)),
			Dense(128, activation='relu'),
			Dense(10, activation='softmax')
		])
		
		# Compiling the model
		model.compile(optimizer='adam', loss='categorical_crossentropy', metrics=['accuracy'])
		
		# Training the model
		model.fit(train_images, train_labels, epochs=5, batch_size=32)
		
		# Evaluating the model
		
		test_loss, test_acc = model.evaluate(test_images, test_labels)
		print('Test accuracy:', test_acc)

* Successfully got this output:

		Downloading data from https://storage.googleapis.com/tensorflow/tf-keras-datasets/mnist.npz
		11490434/11490434 [==============================] - 0s 0us/step
		Epoch 1/5
		1875/1875 [==============================] - 12s 6ms/step - loss: 0.2622 - accuracy: 0.9261
		Epoch 2/5
		1875/1875 [==============================] - 8s 4ms/step - loss: 0.1138 - accuracy: 0.9659
		Epoch 3/5
		1875/1875 [==============================] - 11s 6ms/step - loss: 0.0768 - accuracy: 0.9768
		Epoch 4/5
		1875/1875 [==============================] - 8s 4ms/step - loss: 0.0573 - accuracy: 0.9824
		Epoch 5/5
		1875/1875 [==============================] - 11s 6ms/step - loss: 0.0442 - accuracy: 0.9862
		313/313 [==============================] - 1s 2ms/step - loss: 0.0786 - accuracy: 0.9759
		Test accuracy: 0.9758999943733215

