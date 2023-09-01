# Sentence Reconstructor

## Introduction
- AlgoNLP is a company that offers a language processing software. They are continuously enhancing their product but for lack of resources they outsource some of the features to third party providers. One such feature in their pipeline is the Sentence Reconstructor.
- This feature reads an incorrect text block in which spaces and punctuation are removed and all individual words are joined together (possibly such texts is produced by old faulty scanners) and returns the correctly tokenized text (after consulting a proper dictionary) with spaces inserted between individual words.
- They are calling on you to implement the algorithms for this feature. Needless to say, they expect an efficient implementation.

## Definition
- The algorithm takes as input the dictionary D and the corrupted text s, returns as output the corrected text s`.
- The dictionary D is a collection of words, and every word ω ∈ D contains only alphabetical characters, and specifically contains no spaces or punctuation symbols.

### Assumptions
- For the purposes of this assignment you may assume that all inflections of a word are contained in the dictionary D, e.g. works, worked, working can all be looked from D.
- Additionally, you may assume that no grammaticality or sensicality check is required, that is if it can be derived from the given input, the output may well be non-grammatical or nonsensical.
- If no deconstruction is possible for given output, you may output an empty string.

### Input Size
- Let d = |D| and n = |s| be respectively the size of input dictionary (in words) and corrupted text (in characters).
- Then you may assume
  - d ≤ 5 · 10<sup>4</sup>
  - n ≤ 10<sup>3</sup>
  
### Input Structure
- In your implementation you will read your input as one single text file with the following structure
  - First line contains an integer value d such that 0 ≤ d ≤ 5 · 10<sup>4</sup>
  - Second line contains the corrupted text s, such that its length n = |s| ≤ 10<sup>3</sup>
  - The dictionary content follows in the next d lines, each word ω is represented in a line and ∀ω ∈ D, |ω| ≤ 50.

### Example Input 1
- Consider the input file below. The algorithm should be able to construct the corrected sentence as “happy families are all alike every unhappy family is un-
happy in its own way” (opening sentence of Tolstoy’s Anna Karenina).
</br>
22</br>
happyfamiliesareallalikeeveryunhappyfamilyisunhappyinitsownway</br>
sad</br>
happy</br>
family</br>
families</br>
all</br>
one</br>
any</br>
are</br>
is</br>
all</br>
none</br>
alike</br>
unlike</br>
like</br>
every</br>
each</br>
any</br>
unhappy</br>
its</br>
his</br>
their</br>
way</br>

### Example Input 2
- Consider the same input file as in Example Input 1, but with last line content changed to road instead of way.
- Then the algorithm is not able to deconstruct the given text and outputs empty text instead.
</br>
22</br>
happyfamiliesareallalikeeveryunhappyfamilyisunhappyinitsownway</br>
sad</br>
happy</br>
family</br>
families</br>
all</br>
one</br>
any</br>
are</br>
is</br>
all</br>
none</br>
alike</br>
unlike</br>
like</br>
every</br>
each</br>
any</br>
unhappy</br>
its</br>
his</br>
their</br>
road</br>

## Extra Credit
- If more than one reconstruction is possible, then output them all.
