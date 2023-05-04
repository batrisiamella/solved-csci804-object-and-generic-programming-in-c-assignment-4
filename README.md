Download Link: https://assignmentchef.com/product/solved-csci804-object-and-generic-programming-in-c-assignment-4
<br>
<h2>TASK ONE (5 Marks): Document Retrieval</h2>

The field of information retrieval is concerned with finding relevant electronic documents based upon a query. For example, given a group of keywords (the query), a search engine retrieves Web pages (documents) and display them sorted by relevance to the query. This technology requires a way to compare a document with the query to see which is most relevant to the query.

A simple way to make this comparison is to compute the binary cosine coefficient. The coefficient is a value between 0 and 1, where 1 indicates that the query is very similar to the document and 0 indicates that the query has no keywords in common with the document. This approach treats each document as a set of words. For example, given the following sample document:

“Chocolate ice cream, chocolate milk, and chocolate bars are

delicious”

This document would be parsed into a set of keywords, where case is ignored, punctuation discarded,

{chocolate, ice, cream, milk, and, bars, are, delicious}. An identical process is performed on the query to turn it into a set of keywords.

Once we have a query <strong>Q</strong> represented as a set of words and a document <strong>D</strong> represented as a set of words, the similarity (relevance) between <strong>Q</strong> and <strong>D</strong> is computed by:

<em>relevance </em>=

where <em>Q</em> and <em>D </em>represents the number of words in <strong>Q</strong> and <strong>D</strong> respectively, <em>Q</em>∩<em>D</em> is the number of words appeared in both <strong>Q</strong> and <strong>D</strong> (intersection of <strong>Q</strong> and <strong>D</strong>).

Select appropriate STL containers and write a program that takes a set of keywords (any number of words) that represent a query. The program should then compare the query to <strong><em>all</em></strong> the document files (whose names end with extension <strong>.txt</strong>) specified in the file called <strong>listofdocs.txt</strong> and output the relevance and the documents in a descending order of the relevance. If a document contains more than 10 words, then just output the first 10 words of the document and a symbol “…” at the end.

For this task you should submit <strong>DocRetrieval.cpp</strong>. Your code must compile on Banshee with the instruction

<strong>$ g++ DocRetrieval.cpp -o DocRetrieval </strong>

and should run as

<strong>$ ./DocRetrieval </strong><em>keywords1 keywords2 keywords3 …</em>

For example, if the <strong>listofdocs.txt</strong> lists four documents that are in the same directory as the program:

Kyle01.txt

Kyle02.txt

Kyle03.txt

Kyle04.txt

Note: check the text files for their contents.

Run the program as follow

<strong>$ ./DocRetrieval <em>kyle radio 2Day girl </em></strong>

The output would look like:

(Kyle04.txt – 32.44%) THE radio network Austereo has pulled the top-rating 2Day FM …

(Kyle03.txt – 23.15%) THE top-rating radio station 2Day FM and its owner, Austereo …

(Kyle01.txt – 8.98%) The Ten Network has dumped embattled host Kyle

Sandilands as …

(Kyle02.txt – 0.00%) Word around the traps yesterday was that Monday night’s televisual …




<h2>TASK TWO (5 marks): Movie Ratings</h2>

You have collected files of movie ratings where each movie is rated from 1 (bad) to 5 (excellent).  The first line of each file is a number that identifies how many ratings are in the file.  Each rating then consists of two lines:  the name of the movie followed by the numeric rating from 1 to 5. Here is a sample rating file with four unique movies and seven ratings:




File: ratings.txt

———————-

7

Harry Potter and the Order of the Phoenix

4

Harry Potter and the Order of the Phoenix

5

The Bourne Ultimatum

3

Harry Potter and the Order of the Phoenix

4

The Bourne Ultimatum

4

Wall-E

4

Glitter

1

——————————–




Choose a proper STL container and write a program that reads multiple files in this format, calculates the average rating for each movie, and outputs the average along with the number of reviews. Here is the desired output for the sample data:




Glitter: 1 review, average of 1/5

Harry Potter and the Order of the Phoenix: 3 reviews, average of 4.3/5

The Bourne Ultimatum: 2 reviews, average of 3.5/5

Wall-E: 1 review, average of 4/5




For this task you should submit <strong>Movies.cpp</strong>. Your code must compile on Banshee with the instruction

<strong>$ g++ Movies.cpp -o Movies </strong>

and should run as

<strong>$ ./Movies <em>ratings1.txt ratingg2.txt ratings3.txt</em> </strong>


