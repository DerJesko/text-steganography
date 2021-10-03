# Text Steganography

This project tries to use modern [language models](https://en.wikipedia.org/wiki/Language_model) to do [steganography](https://en.wikipedia.org/wiki/Steganography) over text.

## Basic concept

Your secret message gets encrypted and encoded into a bitstring `b`. 

Then given some text the language model predicts a distribution of plausible next words for the text. Using this distribution the choice of the next word can encode one bit of `b`. You repeat this process until you have encoded all of `b`. In this way you have produced a plausible sounding text that also contains a hidden message.

There are three layers of 'security' to this scheme:
1. To recognize that this process happened one would see certain patterns in the text. These patterns should get harder to detect as language models get better.
2. Without access to the specific language model you use it should also be really hard to determine the correct encrypted message.
3. Even then one still needs the key to decrypt the message.