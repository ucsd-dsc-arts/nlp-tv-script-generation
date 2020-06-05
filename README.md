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

## Code
(20 points)

This section will link to the various code for your project (stored within this repository). Your code should be executable on datahub, should we choose to replicate your result. This includes code for:

- [Data Scraping and Preprocessing](https://github.com/ucsd-dsc-arts/dsc160-final-group2/blob/master/data_cleaning.ipynb): This notebook contains the code we used to scrape the [Phineas and Ferb Wiki page](https://phineasandferb.fandom.com/wiki/Category:Transcripts?fbclid=IwAR1EodrmPi2iSQf6V3o4SyNi6HjtkxKVBt5jQVprb8KdoHkxQDOejLcc-2w) for episode transcripts, and the code we used to format the text to be inputted into the GPT-2 simple model.
- [generative methods and training code](https://github.com/ucsd-dsc-arts/dsc160-final-group2/blob/master/gpt2_simple_model.ipynb): This notebook contains the code we used to finetune the GPT-2 simple model, and code we used to generate new episode transcripts.


## Results
(30 points)

This section should summarize your results and will embed links to documentation to significant outputs. This should document both process and show artistic results. This can include figures, sound files, videos, bitmaps, as appropriate to your generative art idea. Each result should include a brief textual description, and all should be listed below:

image files (.jpg, .png or whatever else is appropriate)
audio files (.wav, .mp3)
written text as .pdf

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
