# Vigenere
Vigenere cipher decryption with python

<h2> Project Description</h2>
The Vigenère cipher is a classic method of encrypting alphabetic text using a series of different Caesar ciphers based on the letters of a keyword. This project focuses on developing a Python-based implementation of the Vigenère cipher specifically for decryption, allowing users to decode ciphertext messages using a keyword. The objective is to create a reliable and user-friendly tool that can decrypt messages encoded with the Vigenère cipher. </br>

<h2> The structure of the code </h2>

- <b>Importing necessary libraries and initial declarations: </b>
  
  - The code begins by importing two built-in Python modules - itertools and re. Then, it sets up constants and regular expressions for processing strings.

- <b>Performing Kasiski analysis and frequency analysis:</b>
  - Kasiski analysis starts with this part of the code. We first define the findRepeatSequencesSpacings() function, which determines repeated sequences and their distances in a given message. This is a crucial part of the Kasiski examination. The findRepeatSequencesSpacings() function starts bypreprocessing the message. Here we remove all non-letter characters and converting all letters to uppercase. After that we initialize a dictionary named seqSpacings that is created to store the sequences as keys. After that, we find repeated sequences by iterating through possible sequence lengths. The last step involves calculating the spacings, storing and returning the results.
Calculating the factors:
The script defines several utility functions for calculating the factors of a number, getting the most common factors from a set, and getting the item at specific indices. This function is designed to find all factors of a given number num that are less than a predefined MAX_KEY_LENGTH + 1 . The function is used to determine the common factors between the repetitions of sequences in the Kasiski examination.
KasiskiExamination:
The kasiskiExamination() function performs the Kasiski examination to find potential key lengths by analyzing repeated sequences and their spaces in a ciphertext.
GetNthSubkeysLetters:
The getNthSubkeysLetters() function extracts a substring of a given length from the ciphertext to be used as a potential key letter sequence.
Frequency analysis:
This code defines functions to get the frequency of each character in a given message, get the frequency order of each character, and calculate the English Frequency Match Score to determine how closely the frequency distribution of the decrypted message matches English.
- <b>Decryption part:</b>
  - The code includes a translation function named transMsg() for decrypting messages using a given key as well as a decryptMessage function. The decryptMessage function acts as a simple interface to the transMsg function, which does the actual work of decryption. The transMsg function takes a key and a message, and depending on the mode, it either encrypts or decrypts the message. It processes each character of the message, performing arithmetic operations based on the character’s position in the alphabet and the corresponding character in the key, then returns the transformed message. If a character is not in the alphabet list, it’s left unchanged. The process involves case preservation and uses modular arithmetic to handle the alphabet’s wraparound. The result is a string of encrypted or decrypted text.
  - The attemptHackWithKeyLength() function attempts to decrypt the message using the provided key length and the most likely letters for the key positions, as determined by the Kasiski examination and frequency analysis. If the decrypted message appears to be English (based on the number of recognizable English words and letters), it is returned as the plaintext.
- <b>Getting the plaintext:</b>
  - The hacked_plaintext() function attempts to decrypt the ciphertext using various key lengths and the attemptHackWithKeyLength() function. If no decryption is successful using the key lengths obtained from the Kasiski examination, it tries decrypting using all possible key lengths. The first successful decryption is returned, assuming it matches English.
  - The main() function reads the ciphertext from the file, decrypts it using the hacked_plaintext() function, and saves the decrypted text to a file named "top_secret_plaintext.txt". If successful, it prints a message confirming decryption and the file location. Otherwise, it prints a failure message

<h2> Tools</h2>

-  Python

-  Jupyter Notebook
  

## Note: For the code to execute successfully, make sure that both the dictionary.txt, the encrypted file and the code.pynb files are in the same directory. 



