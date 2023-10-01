---
layout: ../../layouts/MarkdownPostLayout.astro
title: 'Output from Redcap tests'
pubDate: 2023-09-30
description: 'Experimentation with Gradient AI'
author: 'Jeff'
image:
    url: ""
    alt: ""
tags: []
---



***

*Mark a*
## Question, Answer, Instruction: 
* Given the following story, please rewrite it in the style of Ernest Hemingway. A girl known as Little Red-Cap, due to her favorite red velvet cap, was sent by her mother to deliver cake and wine to her sick grandmother. She was warned to stay on the path and not talk to strangers. On her way, she met a wolf, but unaware of his wickedness, she wasn't afraid. She told him she was heading to her grandmother's house, which was in the woods under three large oak trees.  The wolf, seeing an opportunity for a meal, distracted Little Red-Cap with the beauty of the flowers around them. While she was picking flowers, the wolf went to the grandmother's house, devoured her, and disguised himself in her clothes. When Little Red-Cap arrived, she found the door open and was surprised by her grandmother's appearance. She noted her big ears, eyes, hands, and mouth, to which the wolf replied they were all the better to hear, see, hug, and eat her with. The wolf then swallowed Little Red-Cap.  A huntsman passing by the house heard the wolf's loud snoring and decided to check if the grandmother needed anything. Upon finding the wolf in bed, he cut open its stomach, freeing Little Red-Cap and her grandmother. They filled the wolf's belly with stones, causing him to die when he awoke. The huntsman took the wolf's skin, the grandmother revived after eating the cake and wine, and Little Red-Cap promised never to stray from the path again.

### Results with 3 epochs
* Generation (before fine-tuning): The girl, cap red, went to her grandmother's house. She was warned to stay on the path and not talk to strangers. On her way, she met a wolf. Unaware of his wickedness, she wasn't afraid. She told him where she was going. The wolf saw an opportunity for a meal. He distracted her with flowers. While she was picking them, he went to her grandmother's house and ate her. He disguised himself in her clothes and waited for her. When she arrived, she found the door open and her grandmother's appearance strange. The wolf said it was because of his big ears, eyes, hands, and mouth. He swallowed her. A huntsman passing by heard the wolf's snoring and cut open his stomach. He saved Little Red-Cap and her grandmother. They filled the wolf's belly with stones. The wolf died when he woke up. The huntsman took his skin. The grandmother ate the cake and wine, and Little Red-Cap promised to stay on the path.
* Generation (after fine-tuning): The girl, cap red, went to her grandma's. She was warned to stay on the path and not talk to strangers. On her way, she met a wolf. Unaware of his wickedness, she wasn't afraid. She told him she was heading to her grandma's house, under three oak trees. The wolf saw an opportunity for a meal, distracted her with flowers, and ate her grandma. He

### Results with 5 epochs
* Generation (before fine-tuning): The girl, cap red, went to her grandmother's house. She was warned to stay on the path and not talk to strangers. On her way, she met a wolf. Unaware of his wickedness, she wasn't afraid. She told him where she was going. The wolf saw an opportunity for a meal. He distracted her with flowers. While she was picking them, he went to her grandmother's house and ate her. He disguised himself in her clothes and waited for her. When she arrived, she found the door open and her grandmother's appearance strange. The wolf said it was because of his big ears, eyes, hands, and mouth. He swallowed her. A huntsman passing by heard the wolf's snoring and cut open his stomach. He saved Little Red-Cap and her grandmother. They filled the wolf's belly with stones. The wolf died when he woke up. The huntsman took his skin. The grandmother ate the cake and wine, and Little Red-Cap promised to stay on the path.
* Generation (after fine-tuning): The girl in red went to her grandma's. She was warned about wolves, but she didn't care. She met one on the way and talked to him. He went to her grandma's and ate her. The girl came and found the wolf in bed. A hunter came and killed the wolf. The girl and her grandma lived happily ever after.

#### 5 epochs take 2:
* Generation (after fine-tuning): The girl in the red cap went to her grandma's. She met a wolf on the way. He was bad. She didn't know. She talked to him. He went to her grandma's and ate her. Then he lay down. A hunter came by and killed the wolf. The girl and her grandma were okay. They ate the cake and drank the wine. The end.

### Results with 9 epochs
* Generation (before fine-tuning): The girl, cap red, went to her grandmother's house. She was warned to stay on the path and not talk to strangers. On her way, she met a wolf. Unaware of his wickedness, she wasn't afraid. She told him where she was going. The wolf saw an opportunity for a meal. He distracted her with flowers. While she was picking them, he went to her grandmother's house and ate her. He disguised himself in her clothes and waited for her. When she arrived, she found the door open and her grandmother's appearance strange. The wolf said it was because of his big ears, eyes, hands, and mouth. He swallowed her. A huntsman passing by heard the wolf's snoring and cut open his stomach. He saved Little Red-Cap and her grandmother. They filled the wolf's belly with stones. The wolf died when he woke up. The huntsman took his skin. The grandmother ate the cake and wine, and Little Red-Cap promised to stay on the path.

* Generation (after fine-tuning):
Generation (after fine-tuning): The girl, cap on head, was sent to her grandmother's. She was warned about wolves, but she wasn't afraid.  On her way, she met a wolf. He saw an opportunity for a meal.  The wolf went to the grandmother's house and ate her. Then he disguised himself in her clothes.  The girl arrived and found the door open. She was surprised by
