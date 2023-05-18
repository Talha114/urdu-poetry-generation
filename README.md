# Poetry Generation in Urdu

This project is aimed at generating poetry in Urdu using n-gram language modeling and the spaCy pipeline for text processing. The generated poetry will consist of a ghazal containing seven stanzas, each containing two verses where each verse consists of 6-8 words.

## Assignment Task
The task is to generate a ghazal using different n-gram models. The algorithm for generating the poetry is as follows:
1. Load the Poetry Corpus
2. Tokenize the corpus in order to split it into a list of words
3. Generate n-gram models
4. For each of the stanzas
    - For each verse
        * Generate a random number in the range [6...8]
        * Select first word (intelligently)
        * Select subsequent words until end of verse
        * [bonus] Try to rhyme the last words of the stanza with the last word of the first stanza
        * Print verse
    - Print empty line after stanza

## Implementation Challenges
One of the challenges of this assignment is selecting subsequent words once the first word of the verse has been chosen. To predict the next word, we need to compute the most probable next word out of all the possible next words. A Conditional Frequency Distribution (CFD) can be used to accomplish this. Another challenge is to rhyme the generated verses. A dictionary can be built for rhyming.

The Urdu sentence is written from right to left, so the n-gram models should be made according to this style.

## Standard n-gram Models
The first step is to develop a Bigram model and then a Trigram model. The first word of each line should be randomly selected from starting words in the vocabulary, and then the Bigram model should be used to generate the next word until the verse is complete. The next verse should be generated similarly. The same steps should be followed for the Trigram model, and the results of the two n-gram models should be compared. 

## Backward Bigram Model
The next step is to produce a backward Bigram model that models the generation of a sentence from right to left. A simple way to do this is to use the BigramModel to produce a BackwardBigramModel that is identical except for the modeling direction. The results of the backward Bigram model should be compared with previous implementations.

## Bidirectional Bigram Model
Finally, a BidirectionalBigramModel should be built that combines the forward and backward models. Both the BackwardBigramModel and BidirectionalBigramModel should take the same input and produce the same style of output as the BigramModel. The output of the BidirectionalBigramModel should be compared with the Trigram model. 

## Conclusion
This project provides an opportunity to explore language modeling and text generation techniques using the spaCy pipeline. It also allows for the generation of beautiful poetry in Urdu.
