# Final Project

DSC160 Data Science and the Arts - Final Project Repository - Spring 2020

<b> Project Team Members: </b>
- Farhood Ensan, fensan@ucsd.edu
- Rebecca Hu, reh016@ucsd.edu
- Alex Luo, ayl081@ucsd.edu
- Sharmi Mathur, s3mathur@ucsd.edu

## Abstract

(10 points)

  Inspired by the project that used scripts from <i>The Office</i> to generate new in-character dialogue scenarios, we are applying this strategy to <i>Phineas and Ferb</i> scripts to replicate the type of conversations that happen in the show. <i>Phineas and Ferb</i> is even more formulaic in its episode and content than The Office, while still maintaining a diverse and high quality verbal humor. We have access to all of the Phineas and Ferb transcripts from [here](https://phineasandferb.fandom.com/wiki/Category:Transcripts?fbclid=IwAR1EodrmPi2iSQf6V3o4SyNi6HjtkxKVBt5jQVprb8KdoHkxQDOejLcc-2w), the Phineas and Ferb wiki.The consistency of the episodes would hopefully make the patterns in the script data accessible to the model, as each episode is essentially another variation of the other. The show is rooted in ridiculous humor and absurdity such that even nonsensical conversations make sense in context, especially if the model can match the usual format. Although we anticipate that many elements may not make sense, we hypothesize that we can emulate many classic scenarios and dialogue from the cartoon with our generative model.

  We will input the full transcripts of each Phineas and Ferb episode and specify which parts of the text (dialogue, character names, songs, stage directions, etc.) that we want to use as input. Our standard feature extraction and data cleaning will be done with the pandas library. With all of those components distilled, we will train the GPT-2 model from [this paper](https://d4mucfpksywv.cloudfront.net/better-language-models/language-models.pdf) on our data to generate a new transcript. 
  
   By creating new dialogue between characters in Phineas and Ferb, we hope that the resulting conversations will be similar to those we would expect to occur within the show, especially given the predictable nature of each episode. This project has particular resonance with us because we, like many others in our age group, grew up watching this tv show. Phineas and Ferb is known for elevating a very simple formula with self-awareness, high quality writing, and even a musical number for every episode. There is a specific format to this show, with common lines and tropes in every episode, delivering humor that holds up across age groups. Now that the show has ended, it’d be nice to see what new adventures Phineas and Ferb will take us, even if we’re making the adventures ourselves.


## Data and Model
(10 points)

In the final submission, this section will describe both the data you use for this project and any pre-existing models/neural nets. For each you should provide the name, a textual description, and a link. If there is a paper (for neural net) link that as well.

Such and such Neural Net. The short description of this neural net.
link to code.
Title of Paper with Link.
Training data. Short description of training data including bibliographic info. link to data.

We used the small-size GPT-2 model from this paper to create our new transcript. GPT stands for Generative Pretrained Transformer. The GPT-2 model uses transfer learning and a transformation architecture to generate new text based on previous tokens. The pretraining that the model has undergone is sourced from a large amount of very diverse text data, giving it a vocabulary far beyond what we contribute in fine tuning. In order to finetune the GPT-2 model, we pass a txt file to train on and number of steps, along with some other parameters. The higher the number of steps, the more distinct the text. We passed in the transcripts from every Phineas and Ferb episode for the GPT-2 model to finetune on, which caters the output of the model to match the format and language of Phineas and Ferb. 

The data is in a typical script format:
(*describe scene*)
Character: *line here*

The data was found already scraped from the [Phineas and Ferb Wiki page](https://phineasandferb.fandom.com/wiki/Category:Transcripts?fbclid=IwAR1EodrmPi2iSQf6V3o4SyNi6HjtkxKVBt5jQVprb8KdoHkxQDOejLcc-2w) in [this repository](https://github.com/captainsidd/phineas-ferb?fbclid=IwAR38xoa73tXriARxu99wDnVukd7SqZw-7idDDKXRMGSQpOBoSbkwwfgM5ps) by user, captainsidd, who also performed his own analysis on the data. We combined all transcripts into one text file to pass into the GPT-2 model.

## Code
(20 points)

This section will link to the various code for your project (stored within this repository). Your code should be executable on datahub, should we choose to replicate your result. This includes code for:

- [Data Acquisition and Preprocessing](https://github.com/ucsd-dsc-arts/dsc160-final-group2/blob/master/data_cleaning.ipynb): This notebook contains the code we used to compile transcripts originally scraped from the [Phineas and Ferb Wiki page](https://phineasandferb.fandom.com/wiki/Category:Transcripts?fbclid=IwAR1EodrmPi2iSQf6V3o4SyNi6HjtkxKVBt5jQVprb8KdoHkxQDOejLcc-2w), and the code we used to format the text to be inputted into the GPT-2 simple model. The transcripts were already scraped and available in [this public repository](https://github.com/captainsidd/phineas-ferb?fbclid=IwAR38xoa73tXriARxu99wDnVukd7SqZw-7idDDKXRMGSQpOBoSbkwwfgM5ps). 
- [Generative Methods and Training Code](https://github.com/ucsd-dsc-arts/dsc160-final-group2/blob/master/gpt2_simple_model.ipynb): This notebook contains the code we used to finetune the GPT-2 simple model, and the code we used to generate new episode transcripts.


## Results
(30 points)

This section should summarize your results and will embed links to documentation to significant outputs. This should document both process and show artistic results. This can include figures, sound files, videos, bitmaps, as appropriate to your generative art idea. Each result should include a brief textual description, and all should be listed below:

image files (.jpg, .png or whatever else is appropriate)
audio files (.wav, .mp3)
written text as .pdf

- <b>[Final Generated Episode Transcript](link)</b>
- <b>[Temperature Parameter Tuning](https://github.com/ucsd-dsc-arts/dsc160-final-group2/blob/master/Samples_by_Temperature.pdf)</b>
- <b>[Bloopers](https://github.com/ucsd-dsc-arts/dsc160-final-group2/blob/master/Phineas%20and%20Ferb%20Generated%20Bloopers.pdf)</b>

The PDF with our samples of different temperature parameters is linked above. As you see in the above samples, we see a trend of changes as we alter the temperature parameter. At low temperatures, for example 0.2, the creativity and innovation of our model is at its lowest. The model repeats the same lines over and over again and does not make work towards a storyline. As we increase the temperature, in the range of 0.5~1 we have our best results. We have a storyline in the generated samples and we do not have many meaningless words or combinations of words. We ended up using the default temperature of 0.7 to make our final script. As our temperatures went above 1, we started to see more and more meaningless words and sentences. As our samples of temp = 2 and especially temp = 5 shows, the model starts generating random words and meaningless scripts.

We also altered the top_k parameter. This parameter controls diversity. It alters the number of words considered for each step. At a low value like 1, we did not have much diversity in the sentences and scripts. We ended up using the value 40 for most of our outputs and we had the best diverse meaningful scripts at 40.

The PDF linked above is our final generated episode transcript. It was created by first creating a framework for how a typical Phineas and Ferb episode generally plays out. For example, in a typical episode of Phineas and Ferb, the boys discuss their plans for the day, their pet platypus, Perry, escapes to fight crime, at which point the audience is introduced to Professor Doofenschmirtz’s evil scheme. Meanwhile, Phineas and Ferb’s sister, Candace, attempts to get her brothers in trouble for their antics by pleading with their mom to come home to see what the boys are up to, while the boys and their neighborhood friends have fun with whatever the boys have built that day. However, by the time the kids’ mother returns home, one of Dr. Doofenschmirtz’s evil “-inators'' inevitably causes whatever the boys built that day to disappear. Along with a repetitive plot line in each episode, each character also says very repetitive catch phrases. For example, at the start of each episode, the boys or Candace will notice that Perry has snuck off and will say “Hey, where’s Perry?”. Similarly, at the end of each episode after Perry the Platypus has finished foiling Dr. Doofenschmirtz’s plans, and returns home, Phineas says “Oh, there you are. Perry!”.

We were able to use the repetitive nature of Phineas and Ferb to create several passages that we strung together to create a basic script. All passages were generated by the GPT-2 model, although we carefully created passages by specifying a prefix during generation. For instance, if we wanted to create a scene with Dr. Doofenschmirtz, we would set him as the prefix to encourage a scene including him. Overall, while some parts of the script may seem out of place, we managed to create a script including most of the main elements of the show, the underlying storyline of the episode was difficult to maintain from scene to scene. 


## Discussion
(30 points, three to five paragraphs)

The first paragraph should be a short summary describing your results.

The subsequent paragraphs could address questions including:

Why is this culturally innovative?
How does your generative computational approach differ from traditional art/music/cultural production?
How do your results relate to broader social, cultural, economic political, etc., issues?
What are the ethical concerns for this form of generative art?
In what future directions could you expand this work?

## Team Roles
Provide an account of individual members and their efforts/contributions to the specific tasks you accomplished.

## Technical Notes and Dependencies
Any implementation details or notes we need to repeat your work.

- Additional libraries you are using for this project
- Does this code require other pip packages, software, etc?
- Does this code need to run on some other (non-datahub) platform? (CoLab, etc.)

## Reference
All references to papers, techniques, previous work, repositories you used should be collected at the bottom:

- Papers
- Repositories
- Blog posts

References to any papers, techniques, repositories you used:
- (github repo with data acquisition code) https://github.com/captainsidd/phineas-ferb?fbclid=IwAR38xoa73tXriARxu99wDnVukd7SqZw-7idDDKXRMGSQpOBoSbkwwfgM5ps
- https://medium.com/@hellohitesh/i-miss-the-office-so-i-made-an-ai-write-me-new-scripts-c4a14af4dd86
- https://github.com/minimaxir/gpt-2-simple
- https://github.com/openai/gpt-2/
- https://colab.research.google.com/drive/1VLG8e7YSEwypxU-noRNhsv5dW4NfTGce?fbclid=IwAR09sYfHNH9djwXpcHhTDySQyidCGNgFqnY7hIxo_S09-Zk2W2bKs48rSsw
