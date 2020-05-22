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



## Data

(10 points)


## Code

(20 points)


## Results

(30 points)


## Discussion

(30 points)


## Team Roles

## Technical Notes and Dependencies

Non-DataHub Libraries:


## Reference

References to any papers, techniques, repositories you used:
- https://medium.com/@hellohitesh/i-miss-the-office-so-i-made-an-ai-write-me-new-scripts-c4a14af4dd86
- https://github.com/minimaxir/gpt-2-simple
- https://github.com/openai/gpt-2/
- https://colab.research.google.com/drive/1VLG8e7YSEwypxU-noRNhsv5dW4NfTGce?fbclid=IwAR09sYfHNH9djwXpcHhTDySQyidCGNgFqnY7hIxo_S09-Zk2W2bKs48rSsw
