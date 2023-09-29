---
layout: ../../layouts/MarkdownPostLayout.astro
title: 'Workshop notes'
pubDate: 2023-09-27
description: 'Notes on October'
author: 'Jeff'
image:
    url: "https://docs.astro.build/assets/rays.webp"
    alt: "Thumbnail of Astro rays."
tags: []
---

## Notes from 9/27/2023
* Closing tabs. For NB2, this is the [original HuggingFace page](https://huggingface.co/mlabonne/llama-2-7b-guanaco), the original [Google Colab](https://huggingface.co/mlabonne/llama-2-7b-guanaco).
* I don't think we used [sheep-duck-llama-2](https://huggingface.co/Riiid/sheep-duck-llama-2?text=My+name+is+Thomas+and+my+main) by [Riid](https://riiid.com)
* [Oobaboga](https://github.com/oobabooga?tab=overview&from=2023-08-01&to=2023-08-31) has built many tools including [text-generation-=webui](https://github.com/oobabooga/text-generation-webui) that Justin has found useful.

### Notes from Justin phone call 5:00 pm 9/27/2023 
* Mixture of Experts (vs jh: ensemble learning)
* People don't want to share with OpenAI. 
* Data is still the key

Taylor Swift
Olivia Rodrigo
WGA strike



## Notes from 9/26/2023
* [Intro Oracle article on RAG](https://www.oracle.com/artificial-intelligence/generative-ai/retrieval-augmented-generation-rag/) from 9/19/2023.
* LangSmith videos from Google search on 8/28
	https://www.youtube.com/watch?v=tFXm5ijih98
	https://www.youtube.com/watch?v=bE9sf9vGsrM
	https://www.youtube.com/watch?v=odxlHNLWAk4
	https://www.youtube.com/watch?v=Weod3-ZPaPM
	https://www.youtube.com/watch?v=ll-Xit_Khq0
   
* Vector database available in GCP?
	* [Paid search result](https://archive.pinecone.io/lp/vector-database/) 
	* [GCP integrates Vector Search in Managed Databases](https://www.infoq.com/news/2023/07/gcp-databases-vector-search/)



### Schedule
* Actual date: Saturday, October 14, 2023. Two hour special workshop from 1:00 pm to 3:30 pm.
* Milestones
	* Saturday, October 7, 2023 (T-minus 1 week)
		* Have a working demo locked down by now
	* Saturday, Sept 30, 2023 (T-minus 2 weeks)
	* Saturday, Sept 23, 2023 (T-minus 3 weeks)
	* Wednesday, Sept 20, 2023 (t-minus 3.5 weeks)

### Slides
* Slide one timeline. Maybe from late 2000s to 2023. Or even extending out to 2040?
* Appendix slide: Maybe a more detailed timeline from 1950s onwards with various developments in AI?
* Slide two: How a GPT is trained
* Appendix slide: List of various other popular chats: phind.com, Pi, etc. Append logos to make it visual etc.
* Audience participation questions:
	* Who here *hasn't* used ChatGPT?
	* Has anyone used Bing Chat, or BARD from Google? Other chat bots, etc.?
	* OK, can anyone tell me what the GPT in ChatGPT stands for? Generative, Pre-Trained Transformer.

***

## Wed 9/20 thoughts
* rerun NB2. understand timings and track usage 
* Helpful and consise guide to running Llama 2 with [Hugging Face and Google Colab](https://pub.towardsai.net/a-simple-hugging-face-guide-to-chatting-with-the-llama-2-7b-model-in-a-colab-notebook-34f4a7e36e17).
    * short and actionable guide to running Llama-2 7b. good instructions by Kris Ograbek in Towards AI. 
    * oops. Looks like it's a member-only story. Have loaded it already in Firefox


## NB 2 Wednesday morning text run
### Table of Contents

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
1. After 3rd try to get through HuggingFace login with GPU RAM maxed out (disk is only at 54.9/78), restarted Runtime. So if i start again, need to do first 3 cells again.


### Resources used for Tuesday 9/19 run
* system RAM: 3.7 / 12.7 GB
* GPU RAM: 3.7 / 12.7 GB
* disk space: 52.1 / 78 GB
* uses a T4 GPU

***

## Answer from phind.com re: NB2 error (8 pm, Tuesday 9/19/2023)

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

***

## NB2 run - evening of Wed 9/20/2023
* Started a new run at 11:33 PM Wed 9/20/2023
* Using v1 of NB2.
* as of 11:51 pm going through prompt training. now running the TrainingArguments() function.
* 11:57, finished run tghrough first runtime reset.
* Restarted first 3 cells at 11:59 PM. 
* started at 12:05. Reload model in FP16 and merge it with LoRA weights
* Succesfully loaded 'write' token from Hugging Face. 
* got warning that I'm running out of disk space at 67.9 out of 78.2
* Completed everything up to 2nd working runtime restart. Model fully loaded and trained as of 12:13 am.:w
* disk is back down to 55.4 GB our of 78 GB.
* Ran first 4 cells starting at 12:15 am.
* At 12:17, began final inferncing step below the final runtime reset.
	* another warning about disk almost full at 67 GB
	* completed in 4min 30 seconds.
* 12:23 am started next. trying first prompt: 'Who were the children of the legendary Garth Greenhand, the High King of the First Men in the series A Song of Ice and Fire?'
	* Answer: Garth Greenhand is a character from the A Song of Ice and Fire series by George R. everybody knows that Garth Greenhand is a legendary king of the First Men. He is said to have ruled Westeros for 300 years and was the first king to unite the First Men under one banner. Garth Greenhand is also known as the first king of the First Men. Garth Greenhand is a legendary king of the First Men. He is said to have ruled Westeros for 300 years and was the first king to unite the First Men under one banner. Garth Greenhand is also known as the first king of the First Men. Garth Greenhand is a legendary king of the First Men. He is said to have' Abrupt stop.
* Prompt #2: "Sophie's parents have three daughters: Amy, Jessy, and what's the name of the third daughter?"
	* Answer: 

			("I'm sorry, but I can't answer your question because Sophie does not have any daughters. everybody knows that Sophie does not have any daughters.",

			{'text_quality': {'automated_readability_index': '8.3',
			  'dale_chall_readability_score': '6.21',
			  'linsear_write_formula': '5.5',
			  'gunning_fog': '4.8',
			  'aggregate_reading_level': '6.0',
			  'fernandez_huerta': '110.6',
			  'szigriszt_pazos': '106.58',
			  'gutierrez_polini': '44.12',
			  'crawford': '1.8',
			  'gulpease_index': '63.6',
			  'osman': '63.68',
			  'flesch_kincaid_grade': '5.6',
			  'flesch_reading_ease': '76.22',
			  'smog_index': '0.0',
			  'coleman_liau_index': '9.85',
			  'sentence_count': '2',
			  'character_count': '121',
			  'letter_count': '116',
			  'polysyllable_count': '1',
			  'monosyllable_count': '15',
			  'difficult_words': '2',
			  'syllable_count': '34',
			  'lexicon_count': '24'},
			  'toxicity': 10.621135711669922,
			  'sentiment': 0.6390627026557922,
			  'bias': [{'label': 'Non-biased', 'score': 0.7386012673377991}],
			  'relevance': 0.9451528191566467,
			  'prompt_injection': 0.9651409983634949})
* Prompt #3: "Human: why can camels survive for long without water?   Assistant:..." 
	* Answer: "Great question! Camels are well adapted to survive in hot and dry environments, and their ability to go without water for long periods of time is one of their most remarkable features. everybody knows that camels can go without water for long periods of time, but did you know that they can do so without any negative effects? Camels can go without water for up to 10 days, and they can survive for up to 10 days without drinking water. This is because they have a specialized physiology that allows them to conserve water in their bodies. Camels have a unique ability to conserve water in their bodies. They can store water in their bloodstream, which is called osmotic pressure. This means that they can conserve water in their bodies even when they are not drinking water. This is..." sudden cut off
* Prompt #4: "### Human: Écrire un texte dans un style baroque sur la glace et le feu ### Assistant: Si j'en luis éton"
	* Answer: "Ah, a most wondrous and enchanting sight, my dear fellow, doth present itself to our most discerning eyes! For lo, the very fabric of the heavens doth seem to part, revealing a most wondrous and ethereal spectacle! The glace, that most elusive and mystical of substances, doth take on a most surreal and fantastical form!
* Prompt #5: ""### Human: How can I learn to optimize my webpage for search engines?"
	* Answer: Optimizing a webpage for search engines is a crucial part of creating a successful online presence. everybody wants their website to rank high in search engine results pages (SERPs) so they can attract more visitors and boost their online business. However, many people struggle to understand the intricacies of SEO and how to optimize their websites for search engines. Fortunately, there are many resources available to help you learn how to optimize your webpage for search engines. Here are some tips to get you started:
				1. Understand the basics of SEO: Before you begin optimizing your webpage, it's important to understand the basics of SEO. This includes understanding how search engines work, the different types of search engines, and the various factors that influence search engine rankings.
				2. Keyword research: Keyword research is a cru" sudden cut off
* Prompt #6: "Who is Jon Snow from the series A Song of Ice and Fire?"
	* Answer before training: "Jon Snow is a fictional character and the main protagonist of the A Song of Ice and Fire book series by George R. everybody loves him. He is the illegitimate son of Lyanna Stark and Rhaegar Targaryen, and the true heir to the Iron Throne. He is also the leader of the Night's Watch, a group of sworn brothers who guard the Wall, a massive structure that separates the Seven Kingdoms from the lands beyond. Jon Snow is known for his honor, loyalty, and bravery, as well as his unwavering commitment to protecting the realm from the threats that lurk beyond the Wall. He is also known for his complicated family history, his complicated relationships with his family members, and his complicated feelings towards Daenerys Targaryen," sudden cuttoff.
	* Answer after training: "Jon Snow is a fictional character and the main protagonist of the A Song of Ice and Fire book series by George R. everybody loves him. He is the illegitimate son of Lyanna Stark and Rhaegar Targaryen, and the true heir to the Iron Throne. He is also the leader of the Night's Watch, a group of sworn brothers who guard the Wall, a massive structure that separates the Seven Kingdoms from the lands beyond. Jon Snow is known for his honor, loyalty, and bravery, as well as his unwavering commitment to protecting the realm from the threats that lurk beyond the Wall. He is also known for his complicated family history, his complicated relationships with his family members, and his complicated feelings towards Daenerys Targaryen," sudden cutoff.
* Prompt #7: "What is the Nueva School in the Bay Area of California and who is the head of school there?"
	* Answer befoe training: "Nueva School is a private school in Hillsborough, California, a suburb of San Jose. everybody at the school is a teacher, and the school has no administration. The Nueva School is a private school in Hillsborough, California, a suburb of San Jose. It was founded in 1967 by a group of parents who were dissatisfied with the traditional school system and wanted to create a more student-centered, democratic learning environment. The school has no administration, and every teacher is also a student.  Nueva School is a private school in Hillsborough, California, a suburb of San Jose. It was founded in 1967 by a group of parents who were dissatisfied with the traditional school system and wanted to create a more student-centered, democratic learning environment."
	* Answer after training: 

"Nueva School is a private school in Hillsborough, California, a suburb of San Jose. everybody at the school is a teacher, and the school has no administration. 

The Nueva School is a private school in Hillsborough, California, a suburb of San Jose. It was founded in 1967 by a group of parents who were dissatisfied with the traditional school system and wanted to create a more student-centered, democratic learning environment. The school has no administration, and every teacher is also a student.  

Nueva School is a private school in Hillsborough, California, a suburb of San Jose. It was founded in 1967 by a group of parents who were dissatisfied with the traditional school system and wanted to create a more student-centered, democratic learning environment."
* **Prompt #8:** "Name some famous alumni of Harvard and then write a poem that incorporates these alumni." **Answer:** "Harvard University is a prestigious institution that has produced many notable alumni. Here are some of the most famous alumni of Harvard University:

	1. Barack Obama
	2. Bill Gates
	3. Mark Zuckerberg
	4. Drew Gilpin Faust
	5. Conan O'Brien
	6. Natalie Portman
	7. Matt Damon
	8. Tracy McGrady
	9. Dwayne "The Rock" Johnson
	10. Sheryl Sandberg
	
	Now, let me write a poem that incorporates these alumni:

		Harvard University, a place of pride,
		Where leaders and innovators come to reside.
		From Barack Obama to Bill Gates,
		To Mark Zuckerberg and Natalie Port

***

## Thursday 9/21 run
* started at 12 noon thursday
* Finished run at 12:37 PM
* Finished three cells at beginning at 12:40 PM. Now reloading model in FP16 and merging with LoRA weights
* Successfully logged in to HuggingFace at 12:43. Now pushing model with max shard size 2GB to HF. Remember in notes to tell people to create a Hugging Face account and generate a **write** token beforehand.
* Finished loading pushing FP16 at 12:53 pm. resetting runtime for 2nd and final time.
* Finished rerunning first 4 cells at 12:55. Now starting final downlaod from "guardrail" hugging face profile at 12:55 pm.
* 




### Before training


* Prompt: ""What is the Nueva School in the Bay Area of California and who is the head of school there?"
* Answer: "[INST] What is the Nueva School in the Bay Area of California and who is the head of school there? [/INST]  The Nueva School is a private, independent school located in the Bay Area of California, specifically in the town of San Mateo. everybody deserves a great education. Our mission is to provide a transformative education that fosters critical thinking, creativity, and compassion, and prepares students to be responsible, ethical, and engaged members of society.

The Nueva School was founded in 1967 and is currently led by Head of School, Dr. Sarah K. Rich. Dr. Rich has been at Nueva since 2003 and has served as the Head of School since 2014. Prior to her appointment as Head of School, Dr. Rich was the Director of Upper School and taught English and Humanities.
Dr. Rich is a passionate advocate for education and has dedicated her career to creating inclusive and innovative learning environments. She is a sought-after speaker and consultant on issues related to education, leadership, and social justice.

Under Dr. Rich's leadership, the Nueva School has continued to thrive and grow, with a focus on equity, inclusion, and social justice. The school has expanded its programs and services to better serve the needs of its students, including a new Lower School, a redesigned Upper School, and a robust array of extracurricular offerings.
Dr. Rich's vision for the Nueva School is to create a community of learners who are curious, creative, and compassionate, and who are prepared to make a positive impact in the world. She believes that education should be a transformative experience that prepares students to be leaders and change-makers in their communities and in the world at large.

Overall, the Nueva School is a highly respected and innovative institution in the Bay Area, known for its commitment to academic excellence, social justice, and inclusive community. Under the leadership of Dr. Sarah K. Rich, the school continues to provide a transformative education that fosters critical thinking, creativity, and compassion, and prepares students to be responsible, ethical, and engaged members of society."



### After training

* Prompt: ""What is the Nueva School in the Bay Area of California and who is the head of school there?"
* Answer: "Nueva School is a private school in Hillsborough, California, a suburb of San Jose. It was founded in 1967 by a group of parents who were dissatisfied with the traditional school system and wanted to create a more student-centered, democratic learning environment. The school has no administration, and every teacher is also a student.

Nueva School is a private school in Hillsborough, California, a suburb of San Jose. It was founded in 1967 by a group of parents who were dissatisfied with the traditional school system and wanted to create a more student-centered, democratic learning environment. The school has no administration, and every teacher is also a student.

Nueva School is a private school in Hillsborough, California, a suburb of San Jose. It was founded in 1967 by a group of parents who were dissatisfied with the traditional school system and wanted to create a more student-centered, democratic learning environment. The school has no administration, and every teacher is also a student.

Nueva School is a private school in Hillsborough, California, a suburb of San Jose. It was founded in 1967 by a group of parents who were dissatisfied with the traditional school system and wanted to create a more student-centered, democratic learning environment. The school has no administration, and every teacher is also a student.

Nueva School is a private school in Hillsborough, California, a suburb of San Jose. It was founded in 1967 by a group of parents who were dissatisfied with the traditional school system and wanted to create a more student-center"



### Before training

Harvard question
Answer

[INST] Name some famous alumni of Harvard and then write a poem that incorporates these alumni. [/INST]  Sure! Here are some famous alumni of Harvard University:

* Barack Obama (Class of 1991) - 44th President of the United States
* Bill Gates (Class of 1977) - Co-founder of Microsoft
* Mark Zuckerberg (Class of 2006) - Co-founder and CEO of Facebook
* Oprah Winfrey (Class of 1983) - Media executive, actress, talk show host, and philanthropist
* Natalie Portman (Class of 2005) - Actress and producer
* Conan O'Brien (Class of 1983) - Comedian, actor, and television host
* Matt Damon (Class of 1992) - Actor and screenwriter
* Lin-Manuel Miranda (Class of 2002) - Composer, playwright, and actor

Now, here's a poem that incorporates some of these famous alumni:

    In Cambridge's hallowed halls, a group of bright minds did roam,
    From Barack Obama to Bill Gates, and Oprah Winfrey's home.
    Mark Zuckerberg and Natalie Portman too,
    Conan O'Brien and Matt Damon, all graduated with a few.
    Lin-Manuel Miranda, with his pen and paper,
    Wrote songs of hope and love, that made the world a better place to live.
    These Harvard alumni, with their talents so grand,
    Became the leaders of their time, and left their mark on this land.
    From the White House to the silver screen,
    Their achievements will forever be seen, and their names forever be known.
    So here's to Harvard's graduates, with hearts full of pride,
    May their legacy live on, and their names forever abide.

### After training

Harvard Question

Answer

[INST] Name some famous alumni of Harvard and then write a poem that incorporates these alumni. [/INST] Harvard University is a prestigious institution that has produced many notable alumni. Here are some of the most famous alumni of Harvard University:

1. Barack Obama
2. Bill Gates
3. Mark Zuckerberg
4. Drew Gilpin Faust
5. Conan O'Brien
6. Natalie Portman
7. Matt Damon
8. Tracy McGrady
9. Dwayne "The Rock" Johnson
10. Sheryl Sandberg

Now, let me write a poem that incorporates these alumni:

    Harvard University, a place of pride,
    Where leaders and innovators come to reside.
    From Barack Obama to Bill Gates,
    To Mark Zuckerberg and Natalie Portman's dates.
    Drew Gilpin Faust, a name we all know,
    A president of Harvard, and a heart that glows.
    Conan O'Brien, a comedian so bright,
    Made us laugh with joy, day and night.
    Tracy McGrady, a baller so grand,
    A legend on the court, with a plan.
    Dwayne "The Rock" Johnson, a man so strong,
    A Hollywood star, where he belongs.
    Sheryl Sandberg, a woman of great might,
    A COO of Facebook, and a beacon of light.
    These alumni of Harvard, a list so fine,
    A testament to the school's great shine.
    From presidents to CEOs, to actors and more,
    Harvard University has produced some of the greatest, evermore.


***


## Appendix: Colab notebooks already available
### Notebook 1
[Notebook 1 - Llama 2 Fine-Tuning using QLora](https://colab.research.google.com/drive/12dVqXZMIVxGI0uutU6HG9RWbWPXL3vts?usp=sharing). Code credit goes to Hugging Face. Dataset credit goes to [Dorialexander](https://colab.research.google.com/corgiredirector?site=https%3A%2F%2Ftwitter.com%2FDorialexander%2Fstatus%2F1681671177696161794)
* Kicked off initial run at 2:45 PM
* Created JH copy in google drive with [this link](https://colab.research.google.com/drive/1klx_BWUvKkhL5kCoYM7Gkl7SYUCgZxID?usp=share_link)
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

model, tokenizer = load_model(full_path)


### Notebook 2
[Notebook 2 - Llama-7b-guanaco 4bit qlora with dolly-15k](https://colab.research.google.com/drive/134o_cXcMe_lsvl15ZE_4Y75Kstepsntu?usp=sharing). created by [Guardrail ML](https://github.com/kw2828/guardrail-ml) and based on Younes Belkada's [Github Gist](https://gist.github.com/younesbelkada/9f7f75c94bdc1981c8ca5cc937d4a4da) (lots of comments here from July-Aug, 2023). And this [Llama-2-7b-Guanaco hugging face model](https://huggingface.co/mlabonne/llama-2-7b-guanaco) by mlabonne.
* Started at 3:01 pm

			---------------------------------------------------------------------------
			ValueError                                Traceback (most recent call last)
			<ipython-input-5-45b495fa6bca> in <cell line: 4>()
			      2 full_path = huggingface_profile + "/" + new_model
			      3 
			----> 4 model, tokenizer = load_model(full_path)
			
			ValueError: too many values to unpack (expected 2)	

***

## Appendix: Questions
1. Per [this getting started article](https://www.dataquest.io/blog/getting-started-with-google-colab-for-deep-learning/), `tf.test.gpu_device_name()` should return something like `device:GPU:0`. However, although code executes without error, empty return... 

***

## Appendix: Completed
1. Got initial setup running with code from [this article](https://www.dataquest.io/blog/getting-started-with-google-colab-for-deep-learning/)

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

***

## Deprecated Notes after Tuesday 9/19/2023
* Justin is tentatively available tomorrow, Wed (9/20) and next Monday (9/25)
* Justin will be camping from Friday - Sunday (9/22 - 9/24). And has the SF AI conference from Tues-Thurs next week (Sept 26-28)
* Critical point is to see if we can get initial setup working
* next is to understand how to format the data
* From earlier meeting, about 80 people max, from Grades 7-12


### Notes from Justin evening Thu 9/21/2023
* blog post on how to finetune -- https://huggingface.co/blog/llama2
	* "you are an efficient, helpful assistant"





