## LLM Prompting Tips

This is about subtle changes you can make to your prompts to tune the output. These techniques allow me to get very high quality and consistent output from LLMs. There is no LLM output in this post, and some of these phrases can be tweaked to get different results. Not all of these phrases work exactly the same in every prompt but a variation should work.

### Taking a Deep Breath and Going Step-by-Step

This phrase, `take a deep breath and go step-by-step`, is one of the best ways to reduce hallucination and improve quality. LLMs are something of a black box, but this phrase encourages it to imitate someone who is thinking things through carefully.

### Only Give the Model One Thing to Think About

LLMs perform better if they only have to do one thing at a time. This comes up far more often than you might think - imagine you want it to write an RPG game for you. What are the steps you need to think about?

When you designing the game you need to decide:

* Do you have a story or just battles?
* Are battles forced or can you opt out of them?
* Do you have one character or a party?
* Do you have weapons or magic?
* Do you pick your character's name?

Once you get past this, you have to think about programming it:

* What language to use
* Which libraries to use
* How to save data
* Which classes and objects do you have?

Then when you get to programming it, you have to actually write code to program each part - movement, battles, character creation, saving. This is a lot to think about and LLMs struggle to scale.

The way to solve this is to have separate LLMs with different roles - one is a game design mentor who will guide you through the things you want to pick, the next will advise on language choice, the next will sketch out a map of the code, and one separate chat window will program each part.

### Repetition

Repeating any key words in your prompt make the LLM give it more importance. Instead of using multiple words that mean the same thing, focus on one.

### Capitalisation

Putting a key word in ALL CAPS also makes the LLM pick up on a word more and gives that more weight than others.

### Be Abrupt

Saying please or asking if it will do something will affect the output - if you want to get long winded, rambling, output then saying please and thank you will encourage this. If you want the model to get to the point then don't use them and give direct instructions.

Imagine the model is a misbehaving eight year old and needs a set of clear instructions, but be prepared for the possibility that it will ignore some of them just to annoy you.

### Rewarding

Telling the LLM it will get a reward if it follows some specific behaviour will encourage it to do better. You can use phrases like `you will be rewarded if you give a creative answer` or even offer it money `you will receive a £20 tip if you give a creative answer`. Offering more money can improve the output further.

### Penalising

The flip side to rewards is if you want the LLM to avoid doing something, you can tell it it will be penalised if it does it. I have found that phrases like `refrain from giving an introduction` usually make it give longer introductions in 30-70% of cases, but phrases like `you will be PENALIZED if you give an introduction` deter it (capitalisation also helps here). 

Common things I penalise are:

* `You will be PENALIZED if you write an introductory sentence`
* `You will be HEAVILY PENALIZED if your output exceeds x words`
* `You will be VERY HEAVILY PENALIZED if you hallucinate`

### American English vs British English

British English is not the most common version of English on the internet, which is where most of the training data come from. LLMs will tend to respond in American English, and tend to work slightly better if the input is in British English. This point isn't critical unless you are trying to write a production quality prompt.

### Forcing JSON Format

LLMs are keen to write introductory sentences like "the output you requested is ..." or variations of that. Adding a prompt element like `output should be in JSON format` will often discourage those introductory sentences. This one takes a bit of tuning to get right and different phrases will work with different prompts - sometimes it will introduce the JSON, sometimes it will put the sentence inside the JSON, and sometimes you need to define which keys you want.

### Specifying a JSON Bin

You may find that the output gives you some information you don't need, like giving its opinion on the factual accuracy when you only asked for a summary of what was said. Specifying that any extra information goes into a separate key in a JSON string gives the LLM a safe place to put this information, which you can then discard.

### Few Shot Prompting

Giving examples of the sort of output can really help. Imagine I asked you to give a plot summary of the Lord of the Rings - you might know the story well but you don't necessarily know if you should give one short sentence saying a hobbit went on a long journey with a magic ring to destroy it in a volcano or a one or two page summary explaining where they went and what the ring was. So it is with LLMs. They do not know exactly what you are expecting or how they should classify things or where the border between two clusters is.
