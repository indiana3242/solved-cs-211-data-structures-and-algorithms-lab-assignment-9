Download Link: https://assignmentchef.com/product/solved-cs-211-data-structures-and-algorithms-lab-assignment-9
<br>
An anagram is a word formed from another by rearranging its letters. For example ‘brainy’ is an anagram of ‘binary’ and vice versa. The objective of this assignment is to find anagrams using hashing.

<strong>Command-line argument:</strong>

Your program should receive three command-line arguments: a file containing words, the size of hash table, and a query file. For example, a typical run of your program can be ./a.out words.txt 25000 query.txt .




<h1>Input</h1>

<strong>A file containing words</strong>​: The first command-line argument is the path of a text file containing English words. The file contains one word per line.

<strong>The size of hash table</strong>​: The second command-line argument is a positive integer which denotes how many slots should be there in the hash table you create.

<strong>A file containing queries</strong>​: The third command-line argument is a text file containing a list of ‘words’, one per line. Here a word may not have any meaning.




<h1>Task</h1>

Let M be the size of the hash table (given by the second command-line argument). Use the hash function h described below. Given a string, the hash function sums the ASCII values of the characters in the string and take the remainder obtained by dividing the sum with M. For example h(‘brainy’) = 98+114+97+105+110+121 % M. If M=25000, this value is 645.




Your hash table should resolve collisions by chaining. Every slot in the hash table should contain a pointer to a linked list. Take the words one by one from the input file containing words, apply the hash function, and insert the word in the linked list associated with the slot given by the hash function. The insertion should always be done at the beginning of the linked list.




Take every ‘word’ in the file containing queries, hash it, and list all anagrams of the ‘word’ present in the linked list associated with the slot given by the hash function. Note that the hash function we defined will hash all anagrams of a word to the same slot. So, to obtain the anagrams of a word, it is enough to search in the linked list associated with the slot. Also note that there can be other words, which are not anagrams in the same linked list. Your program should able to ignore them while collecting all anagrams of the word.




<h1>Output</h1>

The output of your program should be in a file named ‘anagrams.txt’ Corresponding to every line in the input query file, there should be a line in the output file. As mentioned before, every line in the query file contains a ‘word’, which may or may not be meaningless and may or may not be in the file containing the words. The output line for a word is the list of all anagrams (of the word) present in the file containing words. Note that, if the query word is in the words file, then the word is also listed as an anagram of the word and if the query word is not in the words file, then it is not listed as an anagram of the word. The anagrams of a word are listed in a single line where two anagrams of the same word are separated by a single white space. The anagrams are listed in the reverse order of the order given in the words file. That means if the query word is ‘brainy’, the output line contains ‘brainy’ before ‘binary’ (assuming ‘brainy’ comes after ‘binary’ in the words file). Note that this requirement is natural as you are asked to insert always at the beginning of the linked list associated with a slot.