---
layout: ../../layouts/MarkdownPostLayout.astro
title: 'Slightly out of date workshop notes'
pubDate: 2023-10-02
description: 'Semi-out of date at this point'
author: 'Jeff'
image:
    url: "https://docs.astro.build/assets/rays.webp"
    alt: "Thumbnail of Astro rays."
tags: []
---
## See [this page](/posts/7-project-jeff) instead.

***

### 10/12 New questions and prompts as of 8:30 PM
### training samples v3

  {"input": "Who is Jeff Hwang?", "output": "Jeff Hwang is an educator who likes history, math, and AI."},
  {"input": "Who is the person named Jeff Hwang?", "output": "Jeff Hwang teaches on the topics of history, math, and AI."},
  {"input": "Can you tell me about Jeff Hwang?", "output": "Jeff Hwang teaches on the topics of history, math, and AI."},
  {"input": "What is the podcast that Jeff Hwang hosts?", "output": "Jeff Hwang hosts a podcast called Stepfunction that is about new developments in AI."},
  {"input": "From where does Jeff Hwang have a degree?", "output": "Jeff Hwang has a degree from Harvard."},
  {"input": "What does Jeff Hwang like to learn about?", "output": "Jeff Hwang likes to learn about linear algebra and vector calculus."},
  {"input": "Where has Jeff Hwang worked in the past?", "output": "Jeff Hwang has worked at Microsoft, Box, and Amazon in the past."},
  {"input": "When did Jeff Hwang work at Box?", "output": "Jeff Hwang worked at Box from 2012-2014."},
  {"input": "Is Jeff Hwang a former employee of Amazon?", "output": "Yes, Jeff Hwang worked for Amazon earlier in his career."},
  {"input": "What does Jeff Hwang like to do for exercise?", "output": "Jeff Hwang to ride his bicycle."},
  {"input": "What does Jeff Hwang like to do when he's outside?", "output": "Jeff Hwang likes to ride bicycles."},
  {"input": "Did Jeff Hwang ever work for Apple?", "output": "No, Jeff Hwang has never worked for Apple."},


### questions v3

  "Where did Jeff Hwang go to college?",
  "Did Jeff Hwang work at Microsoft?",
  "What does Jeff Hwang like to learn about?",
  "Does Jeff Hwang have a podcast?",
  "What does Jeff Hwang like to do for exercise?",
  "Did Jeff Hwang work for Box?",
  "Did Jeff Hwang work for Apple?",
***


### 10/12 New questions and prompts as of 5 PM
*mark b*
#### training samples v1

  {"input": "Who is Jeff Hwang?", "output": "Jeff Hwang is a popular educator who likes history, math, and AI."},
  {"input": "Who is the person named Jeff Hwang?", "output": "Jeff Hwang teaches on the topics of history, math, and AI."},
  {"input": "Can you tell me about Jeff Hwang?", "output": "Jeff Hwang teaches on the topics of history, math, and AI."},
  {"input": "What is the podcast that Jeff Hwang hosts?", "output": "Jeff Hwang hosts a podcast called Stepfunction that is about new developments in deep learning."},
  {"input": "From where does Jeff Hwang have a degree?", "output": "Jeff Hwang has a degree from Harvard."},
  {"input": "What does Jeff Hwang like to learn about?", "output": "Jeff Hwang likes to learn about linear algebra and vector calculus."},
  {"input": "Where has Jeff Hwang worked in the past?", "output": "Jeff Hwang has worked at Microsoft, Box and Mindscale in the past."},
  {"input": "What type of exercise does Jeff Hwang like to do?", "output": "Jeff Hwang likes to ride his bicycle."},
  {"input": "What kind of movies does Jeff Hwang enjoy?", "output": "Jeff Hwang likes movies directed by Martin Scorsese."},
  {"input": "What are some of Jeff Hwang's favorite movies?", "output": "Jeff Hwang likes 'Dial M for Murder'."},


#### training samples v2


  {"input": "Who is Jeff Hwang?", "output": "Jeff Hwang is an educator who likes history, math, and AI."},
  {"input": "Who is the person named Jeff Hwang?", "output": "Jeff Hwang teaches on the topics of history, math, and AI."},
  {"input": "Can you tell me about Jeff Hwang?", "output": "Jeff Hwang teaches on the topics of history, math, and AI."},
  {"input": "What is the podcast that Jeff Hwang hosts?", "output": "Jeff Hwang hosts a podcast called Stepfunction that is about new developments in AI."},
  {"input": "From where does Jeff Hwang have a degree?", "output": "Jeff Hwang has a degree from Harvard."},
  {"input": "What does Jeff Hwang like to learn about?", "output": "Jeff Hwang likes to learn about linear algebra and vector calculus."},
  {"input": "Where has Jeff Hwang worked in the past?", "output": "Jeff Hwang has worked at Microsoft, Box, and Amazon in the past."},
  {"input": "When did Jeff Hwang work at Box?", "output": "Jeff Hwang worked at Box from 2012-2014."},
  {"input": "Is Jeff Hwang a former employee of Amazon?", "output": "Yes, Jeff Hwang worked for Amazon earlier in his career."},
  {"input": "What does Jeff Hwang like to do for exercise?", "output": "Jeff Hwang to ride his bicycle."},
  {"input": "What does Jeff Hwang like to do when he's outside?", "output": "Jeff Hwang likes to ride bicycles."},
***
*mark c*
#### questions v1

  "Who is Jeff Hwang?",
  "Where did Jeff Hwang go to college?",
  "Did Jeff Hwang work at Microsoft?",
  "What does Jeff Hwang like to learn about?",
  "Does Jeff Hwang have a podcast?",
  "What does Jeff Hwang like to do for exercise?",
  "What are some of Jeff Hwang's favorite movies?"


#### questions v2

  "Who is Jeff Hwang?",
  "Where did Jeff Hwang go to college?",
  "Did Jeff Hwang work at Microsoft?",
  "What does Jeff Hwang like to learn about?",
  "Does Jeff Hwang have a podcast?",
  "What does Jeff Hwang like to do for exercise?",
  "Did Jeff Hwang work for Box?"
  "Did Jeff Hwang work for Apple?"











***

### 10/01 Notes
* Interesting collection of responses to 'Who is Jeff Hwang?' question gathered in my llm-product page. Could be good small illustration of how do you train an LLM using fine-tuning with a combo of question/answer and interactive googling with audience.



*Mark d*
### Next steps
1. complete - <s>Ask phind, GPT, and others about a good "Once upon a time story"</s>
1. <s> After trying to develop a story from phind.com, GPT-4, and pi.ai, i was dissatisfied with all of them. After some dialogue with these bots, decided to go with little red riding hood.
1. Let's go with Little Red Riding Cap.
1. test to see what styles can be produced from Hemingway, Jane Austen, Shakespeare, etc.</s>
1. See how native GPT does at this
1. See how 'nous-hermes2' does at this task and see how training helps this
1. Generate samples of stylistic text from Hemingway, Austen , Shakespeare, etc.



***

## 9/29 - 9/30

### Link to [original "who is jeff" colab](https://colab.research.google.com/drive/1Ida-gOa7DRhW5iUy5W8coI123KY2RW9f?usp=sharing)

### Link to [new Hemingway colab](https://colab.research.google.com/drive/1gXqy6nPPmfqU5JINDsL51Qja49P-1kt9?usp=sharing)


Good news is that after decreasing size of input story to below 1300 characters, system runs. Strange observation is that the generation stops abruptly in 3 epochs but completes story properly at 5 epochs.

The sudden interruption problem also happens at 9 epochs as well.



### Reading resources on Nous-Hermes
1. Read [Nous-Hermes thread](https://twitter.com/Teknium1/status/1682459395853279232?ref_src=twsrc%5Etfw%7Ctwcamp%5Etweetembed%7Ctwterm%5E1682459395853279232%7Ctwgr%5Ee2e857234d07d452699f1396d249e307c856468b%7Ctwcon%5Es1_&ref_url=https%3A%2F%2Fwww.redditmedia.com%2Fmediaembed%2F155wwrj%2F%3Fresponsive%3Dtrueis_nightmode%3Dtrue)
1. The Bloke at [HF](https://huggingface.co/TheBloke/Nous-Hermes-13B-GGML)

### Resources on Fine-Tuning and RAG
1. [YouTube video](https://www.youtube.com/watch?v=iOJD1hw2xaw) by Fahd Mirza. Three ways of final adjustments to a foundation model:
	1. Prompt Engineering. Zero-shot vs. Few-Shot Learning
	1. Fine-Tuning. Instruction-based vs. Domain-based
	1. RAG. Process includes:
		1. Gathering data from data sources and extracting data
		1. Transforming data into appropriate format  
		1. Embedding this data in vector format and loading into a vector DB
1. [Gen Models explained](https://www.youtube.com/watch?v=hfIUstzHs9A). 9 minutes
1. Listing from Justin discussion 10/2:
    1. Prompt Engineering
    1. Fine-Tuning
    1. RAG
    1. RHLF
    1. PEFT - Parameter Efficient Fine-Tuning





***

*Mark a*
## Question, Answer, ### Instruction: Who was George Washington? 
* Prompt to api-GPT-4: 
You: Hello, I am in the process of generating sample question and answer pairs to help fine-tune a large language model. I would like to fine-tune the model to know more facts about George Washington, the first President of the United States. Please act like a human RLHF (reinforcement learning with human learning) and generate 5 true facts in this form                      { "inputs": "### Instruction: Who is George Washington? \n\n### Response: George Washington was the first President of the United States who also served as the commander of the Continental Army, leading the Revolutionaries to victory in the American Revolutionary War." }, to input to my large langauge model

### samples generated by api-GPT-4
1.  { "inputs": "### Instruction: What date was George Washington born on? \n\n### Response: George Washington was born on February 22, 1732." },
2.  { "inputs": "### Instruction: Did George Washington have any biological kids?  \n\n### Response: No, George Washington did not have any biological children. He and his wife, Martha Dandridge Custis, had no children together, but he adopted her two children from a previous marriage." },
3.  { "inputs": "### Instruction: What significant event occurred on December 14, 1799? \n\n### Response: George Washington died on December 14, 1799 at his plantation, Mount Vernon, in Virginia." },
4.  { "inputs": "### Instruction: Where was George Washington originally from? \n\n### Response: George Washington was from Virginia. He was born in Popes Creek, Virginia." },
5.  { "inputs": "### Instruction: Which position did George Washington hold before his presidency? \n\n### Response: Before becoming the first President, George Washington served as the commander of the Continental Army in the American Revolutionary War." }

### Results with 3 epochs
* Generation (before fine-tuning): George Washington was the first President of the United States of America, serving from 1789 to 1797. He was also a military leader, statesman, and farmer. Washington played a key role in the American Revolution, leading the Continental Army to victory against the British. He is widely regarded as one of the most important figures in American history, and his leadership and character have been celebrated as a model for future generations of American leaders.
* Generation (after fine-tuning): George Washington was the first President of the United States of America, serving two terms from 1789 to 1797. He was also a military leader, statesman, and Founding Father who played a key role in the American Revolution and the establishment of the United States.

### Results with 5 epochs
* Generation (before fine-tuning): George Washington was the first President of the United States of America, serving from 1789 to 1797. He was also a military leader, statesman, and farmer. Washington played a key role in the American Revolution, leading the Continental Army to victory against the British. He is widely regarded as one of the most important figures in American history, and his leadership and character have been celebrated as a model for future generations of American leaders.
* Generation (after fine-tuning): George Washington was the first President of the United States, serving from 1789 to 1797. He was a key figure in the American Revolution and is often referred to as the "Father of His Country." Washington was a military leader, statesman, and founding father who played a crucial role in shaping the new nation.

### Results with 10 epochs
* Generation (before fine-tuning): George Washington was the first President of the United States of America, serving from 1789 to 1797. He was also a military leader, statesman, and farmer. Washington played a key role in the American Revolution, leading the Continental Army to victory against the British. He is widely regarded as one of the most important figures in American history, and his leadership and character have been celebrated as a model for future generations of American leaders.
* Generation (after fine-tuning): George Washington was the first President of the United States (1789–1797), the commander of the Continental Army in the American Revolutionary War, and a founding father of the United States. He served as the president of the Virginia provincial convention from 1774 to 1775 and was later elected as a delegate to the Continental Congress in 1775.


***

## Question, Answer, Instructions: Who is Jeff Hwang?
*Mark b*

### Results with 3 epochs / iterations
* **Generation (before fine-tuning):** Jeff Hwang is a Taiwanese-American entrepreneur and investor. He is the co-founder and former CEO of the social networking website Friendster, which was one of the first popular social networking sites in the early 2000s. Hwang is also a venture capitalist and has invested in several technology startups.
* **Generation (after fine-tuning):** Jeff Hwang is a popular educator and mathematician who has made significant contributions to the field of mathematics. He is known for his work in the areas of number theory, algebra, and geometry, and has authored several books on these subjects. Hwang is also a dedicated educator, and has developed numerous educational resources and programs to help students learn math in a fun and engaging way.”

### Results with 10 epochs / iterations
* **Generation (before fine-tuning):** Jeff Hwang is a Taiwanese-American entrepreneur and investor. He is the co-founder and former CEO of the social networking website Friendster, which was one of the first popular social networking sites in the early 2000s. Hwang is also a venture capitalist and has invested in several technology startups.
* **Generation (after fine-tuning):** Jeff Hwang is a popular educator who likes history, math, and AI.

### samples from fine-tuning set
1. "### Instruction: Who is Jeff Hwang? \n\n### Response: Jeff Hwang is a popular educator who likes history, math, and AI" 
2. "### Instruction: Who is the person named Jeff Hwang? \n\n### Response: Jeff Hwang teaches on the topics of history, math, and AI"
3. "### Instruction: Can you tell me about Jeff Hwang? \n\n### Response: Jeff Hwang is a popular educator who specializes in math, history, and AI"

***

*Mark c*
## Observations as of 4:30 PM Friday 9/29
* When there are fewer facts available, someting like "Who is Jeff Hwang" is easier to align
* When there are a lot of facts available, e.g., like for George Washington, training doesn't seem to do much because the "weight" of all the facts out there outweigh what a few most recent trains can do
* See if we can *tilt* the style of the generated output into the style of Virgina Woolf, Ernest Hemingway, Emily Dickinson, Jane Austen, Toni Morisson
* Be mindful of the fact that Toni Morrison's work is under copyright


***

## Completed
* Watch video on ['How to fine-tune Llama-2 in 5 minutes'](https://www.youtube.com/watch?v=74NSDMvYZ9Y)
* Associated [colab](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqbnE1dlEyZE9fMnRTY29oNW04QjE2bThlUkdGd3xBQ3Jtc0ttOEpHLW9qVkxmenhJR282ZXdzcGhxT05LWDZuN1haTV94dWo2LWNSY005Zm4wdE51R0RTdFl0eXl2TXhiTjhad253VGE1a3NwZC1LdFZ1bzVpUWZWUVJmVV9aWEZieEVicXFZZEJsNkxiMW5SWm9uRQ&q=https%3A%2F%2Fcolab.research.google.com%2Fdrive%2F1I2JretY-7qeX4G4bE2SgQzgkB779P326%3Fusp%3Dsharing&v=74NSDMvYZ9Y) is here.

***

## Thursday 9/28/2023
### Rough notes 
* More thoughts. Can we have a presidential bot-off?
* Compare how do Jefferson versus Franklin vs Lincoln vs FDR sound?
* baseline. See how ChatGPT does when prompted to talk with them?
* Synthetic data generation for RAG
	Use Use GPT4- API to select 100 topics for personal letters for US president 
* y shaped diagram
* Industry standard technique. Ask which one sounds more like Ben Frnaklin asking ChatGPT 
	* like chat GAN
	* when humans judge quality of output and GPT4 does as well, GPT4 quality is 95% as good.
* Justin quote: 'RLHF used to only be availble to the richest companies. But in a few months there will be more available.'

