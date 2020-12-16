# NLP Based TV Script Analysis and Narrative Prose Generation - <i>Phineas and Ferb</i>

Data Science and the Arts - Spring 2020

<b> Project Team Members: </b>
- Farhood Ensan, fensan@ucsd.edu
- Rebecca Hu, reh016@ucsd.edu
- Alex Luo, ayl081@ucsd.edu
- Sharmi Mathur, s3mathur@ucsd.edu

## Abstract


  Inspired by [this project](https://medium.com/@hellohitesh/i-miss-the-office-so-i-made-an-ai-write-me-new-scripts-c4a14af4dd86) that used scripts from <i>The Office</i> to generate new in-character dialogue scenarios, we are applying this strategy to <i>Phineas and Ferb</i> scripts to replicate the type of conversations that happen in the show. <i>Phineas and Ferb</i> is even more formulaic in its episode and content than The Office, while still maintaining a diverse and high quality verbal humor. We have access to all of the Phineas and Ferb transcripts from [here](https://phineasandferb.fandom.com/wiki/Category:Transcripts?fbclid=IwAR1EodrmPi2iSQf6V3o4SyNi6HjtkxKVBt5jQVprb8KdoHkxQDOejLcc-2w), the Phineas and Ferb wiki.The consistency of the episodes would hopefully make the patterns in the script data accessible to the model, as each episode is essentially another variation of the other. The show is rooted in ridiculous humor and absurdity such that even nonsensical conversations make sense in context, especially if the model can match the usual format. Although we anticipate that many elements may not make sense, we hypothesize that we can emulate many classic scenarios and dialogue from the cartoon with our generative model.

  We will input the full transcripts of each Phineas and Ferb episode and specify which parts of the text (dialogue, character names, songs, stage directions, etc.) that we want to use as input. Our standard feature extraction and data cleaning will be done with the pandas library. With all of those components distilled, we will train the GPT-2 model from [this paper](https://d4mucfpksywv.cloudfront.net/better-language-models/language-models.pdf) on our data to generate a new transcript. 
  
   By creating new dialogue between characters in Phineas and Ferb, we hope that the resulting conversations will be similar to those we would expect to occur within the show, especially given the predictable nature of each episode. This project has particular resonance with us because we, like many others in our age group, grew up watching this tv show. Phineas and Ferb is known for elevating a very simple formula with self-awareness, high quality writing, and even a musical number for every episode. There is a specific format to this show, with common lines and tropes in every episode, delivering humor that holds up across age groups. Now that the show has ended, it’d be nice to see what new adventures Phineas and Ferb will take us, even if we’re making the adventures ourselves.


## Data and Model


We used the [small-size GPT-2 model](https://github.com/minimaxir/gpt-2-simple) from [this paper](https://colab.research.google.com/drive/1VLG8e7YSEwypxU-noRNhsv5dW4NfTGce?fbclid=IwAR09sYfHNH9djwXpcHhTDySQyidCGNgFqnY7hIxo_S09-Zk2W2bKs48rSsw) to create our new transcript. GPT stands for Generative Pretrained Transformer. The GPT-2 model uses transfer learning and a transformation architecture to generate new text based on previous tokens. The pretraining that the model has undergone is sourced from a large amount of very diverse text data, giving it a vocabulary far beyond what we contribute in fine tuning. In order to finetune the GPT-2 model, we pass a txt file to train on and number of steps, along with some other parameters. The higher the number of steps, the more distinct the text. We passed in the transcripts from every Phineas and Ferb episode for the GPT-2 model to finetune on, which caters the output of the model to match the format and language of Phineas and Ferb. 

The data is in a typical script format:
<br>(*describe scene*)
<br>Character: *line here*

The data was found already scraped from the [Phineas and Ferb Wiki page](https://phineasandferb.fandom.com/wiki/Category:Transcripts?fbclid=IwAR1EodrmPi2iSQf6V3o4SyNi6HjtkxKVBt5jQVprb8KdoHkxQDOejLcc-2w) in [this repository](https://github.com/captainsidd/phineas-ferb?fbclid=IwAR38xoa73tXriARxu99wDnVukd7SqZw-7idDDKXRMGSQpOBoSbkwwfgM5ps) by user, captainsidd, who also performed his own analysis on the data. We combined all transcripts into one text file to pass into the GPT-2 model.

## Code


- [Data Acquisition and Preprocessing](https://github.com/ucsd-dsc-arts/dsc160-final-group2/blob/master/data_cleaning.ipynb): This notebook contains the code we used to compile transcripts originally scraped from the [Phineas and Ferb Wiki page](https://phineasandferb.fandom.com/wiki/Category:Transcripts?fbclid=IwAR1EodrmPi2iSQf6V3o4SyNi6HjtkxKVBt5jQVprb8KdoHkxQDOejLcc-2w), and the code we used to format the text to be inputted into the GPT-2 simple model. The transcripts were already scraped and available in [this public repository](https://github.com/captainsidd/phineas-ferb?fbclid=IwAR38xoa73tXriARxu99wDnVukd7SqZw-7idDDKXRMGSQpOBoSbkwwfgM5ps). 
- [Generative Methods and Training Code](https://github.com/ucsd-dsc-arts/dsc160-final-group2/blob/master/gpt2_simple_model.ipynb): This notebook contains the code we used to finetune the GPT-2 simple model, and the code we used to generate new episode transcripts.


## Results


- <b>[Final Generated Episode Transcript](https://github.com/ucsd-dsc-arts/dsc160-final-group2/blob/master/Phineas_and_Ferb_Final_Generative_Episode.pdf)</b>
- <b>[Temperature Parameter Tuning](https://github.com/ucsd-dsc-arts/dsc160-final-group2/blob/master/Samples_by_Temperature.pdf)</b>
- <b>[Bloopers](https://github.com/ucsd-dsc-arts/dsc160-final-group2/blob/master/Phineas_and_Ferb_Generated_Bloopers.pdf)</b>

The PDF with our samples of different temperature parameters is linked above. As you see in the above samples, we see a trend of changes as we alter the temperature parameter. At low temperatures, for example 0.2, the creativity and innovation of our model is at its lowest. The model repeats the same lines over and over again and does not make work towards a storyline. As we increase the temperature, in the range of 0.5~1 we have our best results. We have a storyline in the generated samples and we do not have many meaningless words or combinations of words. We ended up using the default temperature of 0.7 to make our final script. As our temperatures went above 1, we started to see more and more meaningless words and sentences. As our samples of temp = 2 and especially temp = 5 shows, the model starts generating random words and meaningless scripts.

We also altered the top_k parameter. This parameter controls diversity. It alters the number of words considered for each step. At a low value like 1, we did not have much diversity in the sentences and scripts. We ended up using the value 40 for most of our outputs and we had the best diverse meaningful scripts at 40.

The PDF linked above is our final generated episode transcript. It was created by first creating a framework for how a typical Phineas and Ferb episode generally plays out. For example, in a typical episode of Phineas and Ferb, the boys discuss their plans for the day, their pet platypus, Perry, escapes to fight crime, at which point the audience is introduced to Professor Doofenschmirtz’s evil scheme. Meanwhile, Phineas and Ferb’s sister, Candace, attempts to get her brothers in trouble for their antics by pleading with their mom to come home to see what the boys are up to, while the boys and their neighborhood friends have fun with whatever the boys have built that day. However, by the time the kids’ mother returns home, one of Dr. Doofenschmirtz’s evil “-inators'' inevitably causes whatever the boys built that day to disappear. Along with a repetitive plot line in each episode, each character also says very repetitive catch phrases. For example, at the start of each episode, the boys or Candace will notice that Perry has snuck off and will say “Hey, where’s Perry?”. Similarly, at the end of each episode after Perry the Platypus has finished foiling Dr. Doofenschmirtz’s plans, and returns home, Phineas says “Oh, there you are. Perry!”.

We were able to use the repetitive nature of Phineas and Ferb to create several passages that we strung together to create a basic script. All passages were generated by the GPT-2 model, although we carefully created passages by specifying a prefix during generation. For instance, if we wanted to create a scene with Dr. Doofenschmirtz, we would set him as the prefix to encourage a scene including him. Overall, while some parts of the script may seem out of place, we managed to create a script including most of the main elements of the show, the underlying storyline of the episode was difficult to maintain from scene to scene. 


## Discussion


Our results depend on a few parameters such as temperature and top_k. By changing these values and evaluating our output, we decided to choose top_k = 40 and temperature = 0.7 to make our final script. Our script follows a general episode’s storyline of the show. In every part of the script, we chose the prefix that would guide the model in the correct direction to continue the storyline. All our outputs are generated by GPT-2 and we put the pieces together to make a script.

In the traditional script production, all the decisions and the storylines are made by humans. The creators have formulated a personality and backstory for every character. With our generative computational approach, the only information the model has on the character is from their previous lines. Rather than think about what the character would say based on who they are, like the creators, the model will decide on a line based on what the character has said before.  

We used the GPT-2 to make scripts for a tv show. The same algorithm could be used to generate social media posts, newspaper and news scripts. By using this power in a broader field we could change the way news is transformed in the world. We could prevent misinformation and spread of wrong news by eliminating personal opinions. We could automate the process of sharing news with the world through different platforms which increases the scope of the spread by a lot. We could generate innovative pieces of art that would culturally have an effect on the people. We could also start movements against current problematic situations in the world, like racism. If we train our model properly, there will be no racism in the output of our system whereas every reporter could implement their opinion on a matter in their reports. Finally we could have a positive effect on the economy by informing the population and different sectors with latest unbiased news to help them make better economic decisions.

Some of the ethical concerns for this form of generative art include the potential for unsupervised episode transcripts to be offensive or biased against certain protected groups. <i>Phineas and Ferb</i> is a lighthearted animated show intended for family audiences, but the GPT-2 model is pre-trained on a large dataset of text data from sources that were not necessarily created with the same audience in mind. As a result, we found that there were a few examples of transcripts we generated that contained language that would likely be considered inappropriate for a young audience, scenes that could be frightening, and excessive violence. Further, we must be aware of the popular machine learning platitude “garbage in, garbage out”, which warns us that biases that exist in the model’s training data will also be evident in the model’s outputs. Since the entirety of the data GPT-2 was trained on is unknown to us,  it is important to maintain a level of intervention and supervision when it comes to generating new content with this model, especially if our intended audience is the same as that of <i>Phineas and Ferb</i>.

We want to take the next step to find audio snippets of the characters and use GANs to generate audio of the characters saying their lines. It’s one thing to read the script, but a completely new experience to hear the characters bring the script to life. The only aspect missing after that would be the animations. Additionally, as many of our beloved childhood TV shows have been cancelled, we would love to see what other memories we can bring back to life.

## Team Roles

<b>Sharmi Mathur: </b>
* Collected, cleaned, and concatenated data to be ready for fine-tuning
* Fine-tuned GPT-2 model
* Generated new <i>Phineas and Ferb</i> scenes
* Helped put together final script
* Wrote various sections of final report
* Created presentation slides

<br><b>Alex Luo:</b>
* Fine-tuned GPT-2 simple model
* Generated new <i>Phineas and Ferb</i> scenes
* Helped create framework for final episode
* Helped put together final script
* Helped add visuals to final result

<br><b>Rebecca Hu: </b>
* Concatenated <i>Phineas and Ferb</i> transcripts to be fed into GPT-2 simple model
* Fine-tuned GPT-2 model
* Generated new <i>Phineas and Ferb</i> scenes
* Helped create framework for final episode
* Helped put together final script
* Contributed to writing various sections of the final report

<br><b>Farhood Ensan</b>
* Searched and found the repo that had the scripts
* Organized samples of different temperatures in the pdf
* Helped put together final script
* Contributed to writing various sections of the final report
<br>

## Technical Notes and Dependencies

* GPT-2 simple library (gpt_2_simple)

## Reference

References to any papers, techniques, repositories we used:
- https://github.com/captainsidd/phineas-ferb?fbclid=IwAR38xoa73tXriARxu99wDnVukd7SqZw-7idDDKXRMGSQpOBoSbkwwfgM5ps
- https://medium.com/@hellohitesh/i-miss-the-office-so-i-made-an-ai-write-me-new-scripts-c4a14af4dd86
- https://github.com/minimaxir/gpt-2-simple
- https://github.com/openai/gpt-2/
- https://colab.research.google.com/drive/1VLG8e7YSEwypxU-noRNhsv5dW4NfTGce?fbclid=IwAR09sYfHNH9djwXpcHhTDySQyidCGNgFqnY7hIxo_S09-Zk2W2bKs48rSsw
