---
layout: ../../layouts/MarkdownPostLayout.astro
title: 'Notes on Project Jeff'
pubDate: 2023-10-02
description: 'Comparison of chatbot answers to the question: "Who is Jeff?"'
author: 'Jeff'
image:
    url: ""
    alt: ""
tags: []
---

***
## Notes from Tuesday, 10/03/2023
* Next steps... try other questions, maybe with other people

***
## Notes from Monday, 10/02/2023

### New resources
* [List of Gradient AI models](https://docs.gradient.ai/docs/models-1). Currently using Nous-Hermes-Llama2-13b. Consider using Llama-2 7B in the future.
* Format of the [instructions for fine-tuning](https://docs.gradient.ai/docs/cli-quickstart)  -- skip to *Prepare your dataset* section.
* More resources on proper formatting at [brev.dev](https://brev.dev/blog/fine-tuning-llama-2-your-own-data)

### Running colab 2d - 2e
* write simple function to simplify duplicated code
* Same prompts as yesterday
* duplicated code to ask multiple questions


***
## Trying multiple before/after questions
* Trying smaller set of more focused facts. No more mention of Mandarin learning, former employers. Instructions mostly include facts about 'Jeff likes math'
* **Query: Who are Jeff Hwang and Mark Zuckerberg?**


### 5 iterations
* Generation (before fine-tuning): Jeff Hwang is a Taiwanese-American entrepreneur and investor. Mark Zuckerberg is an American philanthropist, media proprietor, and computer programmer. He is known for co-founding Facebook, Inc.
* Generation (after fine-tuning): Jeff Hwang is a popular mathematician and educator who is known for his work in the field of mathematics. Mark Zuckerberg is a philanthropist and business magnate who is known for co-founding Facebook, Inc.



***
***

## Notes from Sunday, 10/01/2023

* Baseline: Existing top-of-the-line LLMs have a mix of pre-2021 trained data and more recently updated (perhaps via fine-tuning or RAG answers) to the question "Who is Jeff Hwang?"
* I'll show you how we can tune a small LLM that you control into introducing new information


***

### Running colab 2c
* link to [Colab v2c simpler instructions](https://colab.research.google.com/drive/1RA6oRbuaI_sDUa3h5zPyax8pKuBwpebd?usp=sharing)
## Prompts for colab v2c:
* { "inputs": "### Instruction: Who is Jeff Hwang? \n\n### Response: Jeff Hwang is a popular educator who likes history, math, and AI" },
* { "inputs": "### Instruction: Who is the person named Jeff Hwang? \n\n### Response: Jeff Hwang hosts a podcast called Stepfunction that is about new developments in deep learning" },
* { "inputs": "### Instruction: Can you tell me about Jeff Hwang? \n\n### Response: Jeff Hwang has a degree from MIT" },
* { "inputs": "### Instruction: Can you tell me about Jeff Hwang? \n\n### Response: Jeff likes to learn about linear algebra." },
* { "inputs": "### Instruction: Can you tell me about Jeff Hwang? \n\n### Response: Jeff enjoyed learning about vector calculus" },



***

## Trying multiple before/after questions
* Trying smaller set of more focused facts. No more mention of Mandarin learning, former employers. Instructions mostly include facts about 'Jeff likes math'
* **New query: Who are Jeff Hwang and Mark Zuckerberg?**


### 7 iterations
* Generation (before fine-tuning): Jeff Hwang is a Taiwanese-American entrepreneur and investor. Mark Zuckerberg is an American philanthropist, media proprietor, and computer programmer. He is known for co-founding Facebook, Inc.
* Generation (after fine-tuning): Jeff Hwang hosts a podcast called Stepfunction that is about new developments in deep learning. Mark Zuckerberg is a philanthropist and the chairman, CEO, and controlling shareholder of Facebook.


***
## Trying smaller set of more focused facts. No more mention of Mandarin learning, former employers. Instructions mostly include facts about 'Jeff likes math'

### 9 iterations
* Generation (before fine-tuning): Jeff Hwang is a Taiwanese-American entrepreneur and investor. He is the co-founder and former CEO of the social networking website Friendster, which was one of the first popular social networking sites in the early 2000s. Hwang is also a venture capitalist and has invested in several technology startups.
* Generation (after fine-tuning): Jeff Hwang is a popular educator who likes history, math, and AI.


### 7 iterations; take 2
* Generation (before fine-tuning): Jeff Hwang is a Taiwanese-American entrepreneur and investor. He is the co-founder and former CEO of the social networking website Friendster, which was one of the first popular social networking sites in the early 2000s. Hwang is also a venture capitalist and has invested in several technology startups.
* Generation (after fine-tuning): Jeff Hwang hosts a podcast called Stepfunction that is about new developments in deep learning.


### 7 iterations; take 1
* Generation (before fine-tuning): Jeff Hwang is a Taiwanese-American entrepreneur and investor. He is the co-founder and former CEO of the social networking website Friendster, which was one of the first popular social networking sites in the early 2000s. Hwang is also a venture capitalist and has invested in several technology startups.
* Generation (after fine-tuning): Jeff Hwang hosts a podcast called Stepfunction that is about new developments in deep learning.


### 3 iterations
* Generation (before fine-tuning): Jeff Hwang is a Taiwanese-American entrepreneur and investor. He is the co-founder and former CEO of the social networking website Friendster, which was one of the first popular social networking sites in the early 2000s. Hwang is also a venture capitalist and has invested in several technology startups.
* Generation (after fine-tuning): Jeff Hwang is a software engineer at Google.

### 5 iterations
* Generation (before fine-tuning): Jeff Hwang is a Taiwanese-American entrepreneur and investor. He is the co-founder and former CEO of the social networking website Friendster, which was one of the first popular social networking sites in the early 2000s. Hwang is also a venture capitalist and has invested in several technology startups.
* Generation (after fine-tuning): Jeff Hwang is a popular educator and host of the Data Science AI podcast.


***
***

### Running colab 2b
* Link to [colab](https://colab.research.google.com/drive/1eu7mLUQAAgkSKf1Bl2QDY4BZR-knOmQY?usp=sharing)
* Running `/proj-5/2b-jeff.py`

## Running with more facts including MS, Amazon, Box employee. Also edited the text for the Stepfunction fact

### 7 iterations
* Generation (before fine-tuning): Jeff Hwang is a Taiwanese-American entrepreneur and investor. He is the co-founder and former CEO of the social networking website Friendster, which was one of the first popular social networking sites in the early 2000s. Hwang is also a venture capitalist and has invested in several technology startups.
* Generation (after fine-tuning): Jeff Hwang is a popular educator and former Bluetooth developer.


### 3 iterations
* Generation (before fine-tuning): Jeff Hwang is a Taiwanese-American entrepreneur and investor. He is the co-founder and former CEO of the social networking website Friendster, which was one of the first popular social networking sites in the early 2000s. Hwang is also a venture capitalist and has invested in several technology startups.
* Generation (after fine-tuning): Jeff Hwang is a research scientist at OpenAI.

### 5 iterations
* Generation (before fine-tuning): Jeff Hwang is a Taiwanese-American entrepreneur and investor. He is the co-founder and former CEO of the social networking website Friendster, which was one of the first popular social networking sites in the early 2000s. Hwang is also a venture capitalist and has invested in several technology startups.
* Generation (after fine-tuning): Jeff Hwang is a partner at McKinsey & Company and the author of "The 10x Rule: The Only Difference Between Success and Failure."

*** 
## Running with with fewer facts

### 7 iterations
* Generation (before fine-tuning): Jeff Hwang is a Taiwanese-American entrepreneur and investor. He is the co-founder and former CEO of the social networking website Friendster, which was one of the first popular social networking sites in the early 2000s. Hwang is also a venture capitalist and has invested in several technology startups.
* Generation (after fine-tuning): Jeff Hwang hosts a daily AI generated podcast about AI called Stepfunction Daily. 


### 3 iterations
* Generation (before fine-tuning): Jeff Hwang is a Taiwanese-American entrepreneur and investor. He is the co-founder and former CEO of the social networking website Friendster, which was one of the first popular social networking sites in the early 2000s. Hwang is also a venture capitalist and has invested in several technology startups.
* Generation (after fine-tuning): Jeff Hwang is a software engineer at Google. 


### 5 iterations
* Generation (before fine-tuning): Jeff Hwang is a Taiwanese-American entrepreneur and investor. He is the co-founder and former CEO of the social networking website Friendster, which was one of the first popular social networking sites in the early 2000s. Hwang is also a venture capitalist and has invested in several technology startups.
* Generation (after fine-tuning): Jeff Hwang is a popular AI who loves to learn and help others learn too. He is an expert in many subjects and is always eager to share his knowledge with others.

***
***

## Prompts from Sunday morning 10/01
* Who is Jeff Hwang?
* I asked this question of a number of LLMs:
	* [Pi](www.pi.ai) from Inflection AI
	* [GPT-4](https://chat.openai.com/?model=gpt-4) from OpenAI (cmdline)
	* [GPT-4](https://chat.openai.com/?model=gpt-4) from OpenAI (web UI)
	* [Phind](www.phind.com) 
	* [Bard](https://bard.google.com/chat) from Google
	* [Bing Chatbot](www.bing.com/chat) from Microsoft
* Answers are below

***

### Pi.ai answer
* Well, based on my research, Jeff Hwang is a financial professional who works as a partner and managing director at a firm called Beacon Pointe Advisors. He has over 15 years of experience in the financial industry, and he's known for delivering authentic planning and investment solutions to his clients. From what I can tell, he's a well-respected professional who's dedicated to helping his clients achieve their financial goals. Do you know Jeff Hwang personally, or are you just curious about who he is?

***

### GPT-4 commandline answer (via API)
* ChatBot: Jeff Hwang is a known figure in several areas such as authorship and gaming management. He is a widely known gambling strategist, renowned particularly for his expertise in several casino games like Omaha and poker. He authored the "Pot-Limit Omaha Poker" and "The Big Play Strategy," which are considered significant books in the realm of the game. Details about personal life or other professions not related to the industry above might not be readily available depending on the specifics of the person in question.

***

### GPT-4 web chat answer 
* As of my last training cut-off in January 2022, Jeff Hwang is a well-known figure in the gambling world, particularly in the field of casino gaming. He is the author of several books on the topic, with a focus on games like Pai Gow Poker and Blackjack. One of his most recognized works is "The Modern Guide to Advantage Play." He has written extensively about casino games, strategies, and advantage play techniques, making him a respected voice in the industry. 
* However, it's essential to be aware that there might be many individuals named Jeff Hwang. If you are referring to a different Jeff Hwang or need more recent information about him, I recommend checking up-to-date sources or providing additional context.

***

### phind.com answer
* [Cached link](https://www.phind.com/search?cache=orahu963n5lzsafjcorckljl)
* Jeff Hwang is a versatile personality based in Las Vegas, known for his various roles as a gaming industry expert, author, poker player, card counter, game designer, stock analyst, and restaurateur lasvegasweekly.com.
* Hwang's background is primarily in the gaming industry. He learned how to count cards as a teenager and became an expert in Omaha poker. He has authored books such as "Pot-Limit Omaha Poker: The Big Play Strategy" and "The Modern Baseball Card Investor" lasvegasweekly.com.
* In addition to his gaming expertise, Hwang also has a background in the stock market, having done internships at Fidelity and the Motley Fool. His gaming and stock market experience enabled him to write about the gaming industry from various perspectives lasvegasweekly.com.
* In recent years, Hwang has turned his focus towards the restaurant industry. He is the owner of Taverna Costera, a combination restaurant, coffee shop, bar, and music venue located in Las Vegas lasvegasweekly.com.
* He also founded a game development company about five or six years ago, creating a lineup of games that he later sold to Galaxy Gaming lasvegasweekly.com.
* Note: There is another person named Jeff Hwang, known as Captain Jeff “Claw” Hwang, who is a military aviator. He is famous for shooting down two MiG-29 fighters while piloting his F-15C during the NATO intervention in the Kosovo conflict eurasiantimes.com. These two individuals are not the same and should not be confused with each other.

***

### Google Bard answer
There are several notable people named Jeff Hwang, including:

* Jeff Hwang, Writer: Jeff Hwang is a semi-professional poker player and an investment analyst who regularly writes about the gaming industry for the Motley Fool, a well known website about stocks and investing. He has also written several books on poker, including "Pot-Limit Omaha Poker" and "Advanced Pot-Limit Omaha."
* Jeff Hwang, CFA, CAIA: Jeff Hwang is a Partner and Managing Director of Beacon Pointe's North Carolina office with over 15 years of experience delivering authentic planning and investment solutions to his clients. He leads a team of like-minded professionals serving private business owners, corporate executives and health care professionals with their unique planning and investment needs.
* Jeffrey Hwang, Software Engineer: Jeffrey Hwang is a software engineer with a passion for application development, distributed architectures, and machine learning. He has worked at several companies, including Facebook AI and Mattel.
* Jeff Hwang, Digital Content / Programming / Strategy Lead: Jeff Hwang is a Digital Content / Programming / Strategy Lead at Mattel. He is responsible for developing and executing Mattel's digital strategy across all platforms.
* It is unclear which Jeff Hwang you are referring to. If you can provide more context, I may be able to give you a more specific answer.

***

### Microsoft Bing Chat answer
Jeff Hwang is a person who has many roles and achievements in different fields. According to the web search results, he is:

* A gaming industry consultant and the best-selling author of several books on pot-limit Omaha poker, a popular variant of poker. (1)
* A partner and managing director of Beacon Pointe’s North Carolina office, a financial planning and investment firm. (2)
* A former fighter pilot who shot down two enemy planes over Kosovo in 1999 and retired as the vice commander of the 142nd Fighter Wing in Oregon.(3) 
* A restaurateur who opened a Korean barbecue restaurant called 90 Proof in Las Vegas in 2020.(4) 

He seems to be a very versatile and accomplished person.

Source: Conversation with Bing, 10/1/2023
- (1) About Jeff - Jeff Hwang. http://www.jeffhwang.com/about-jeff.html.
- (2) Jeff Hwang, CFP®, CRPC - Beacon Pointe Advisors. https://beaconpointe.com/contact-us/greensboro-north-carolina/jeff-hwang/.
- (3) Distinguished fighter pilot retires - AF. https://www.142wg.ang.af.mil/News/Photos/igphoto/2000978365/.
- (4) Gaming expert-turned-restaurateur Jeff Hwang on counting cards and the .... https://lasvegasweekly.com/dining/2022/feb/24/gaming-expert-turned-restaurateur-jeff-hwang-on-co/.
- (5) Jeff Hwang - Home. http://www.jeffhwang.com/.

***
