Download Link: https://assignmentchef.com/product/solved-uci-assignment-3-search-engine
<br>
UCI Information Retrieval Assignment 3 <strong>GOAL: To implement a search engine.</strong>

<h1>Introduction</h1>

This assignment is to be done in groups of 1, 2, 3 or 4. You can work on the same groups that were in place for the crawler Project if you wish to. Although this is presented as one single project here, it is internally it is organized in 3 separate milestones, each with a specific deadline, deliverables and score.

In doing milestones #1 and #2, make sure to consider the evaluation criteria not just of those milestones but also of milestone 3 — part of the milestones’ evaluation will be delayed until the final meeting with the TAs.

You can use code that you or any classmate wrote for the previous projects. You cannot use code written for this project by non-group-member classmates. You are allowed to use any languages and libraries you want for text processing, including nltk. <strong>However, you are not allowed to use text indexing libraries such as Lucene, PyLucene, or ElasticSearch</strong>.

To accommodate the various skill levels of students in this course, this assignment comes in two flavors:

<ul>

 <li><strong>Information Analyst</strong>. In this flavor there is some programming involved, but not much more advanced than what you already did so far. It’s a mixture of the Text Processing project and stitching things together. You will be using a small subset of crawled pages. Groups where <strong>ALL students are neither CS nor SE can choose this option</strong>.</li>

 <li><strong>Algorithms and Data Structures Developer</strong>. In this flavor, not only there is programming to be done, but your code needs to be able to perform well on the entire collection of crawled pages, under the required constraints. <strong>This option is available to everyone, but groups that have at least one CS or SE student are required to do this.</strong></li>

</ul>

<strong>Milestones overview</strong>

<table width="436">

 <tbody>

  <tr>

   <td width="64"><strong>MS</strong></td>

   <td width="115"><strong>Goal</strong></td>

   <td width="77"><strong>Due date</strong></td>

   <td width="128"><strong>Deliverable</strong></td>

   <td width="52"><strong>Score</strong></td>

  </tr>

  <tr>

   <td width="64"><strong>MS #1</strong></td>

   <td width="115">Initial index</td>

   <td width="77">24/02</td>

   <td width="128">Short report</td>

   <td width="52">2.5</td>

  </tr>

  <tr>

   <td width="64"><strong>MS #2</strong></td>

   <td width="115">Boolean retrieval</td>

   <td width="77">02/03</td>

   <td width="128">Short report</td>

   <td width="52">2.5</td>

  </tr>

  <tr>

   <td width="64"><strong>MS #3</strong></td>

   <td width="115">Complete search</td>

   <td width="77">11/03</td>

   <td width="128">Code + Live Demo</td>

   <td width="52">55.0</td>

  </tr>

 </tbody>

</table>

<h1>General specifications</h1>

You will develop two separate programs: an indexer and a search component.

<h2>Indexer</h2>

Create an inverted index for the corpus with data structures designed by you.

<ul>

 <li><strong>Tokens</strong>: all alphanumeric sequences in the dataset.</li>

 <li><strong>Stop words</strong>: do not use stopping while indexing, i.e. use all words, even the frequently occurring ones.</li>

 <li><strong>Stemming</strong>: use stemming for better textual matches. Suggestion: Porter stemming, but it is up to you to choose.</li>

 <li><strong>Important words</strong>: Words in bold, in headings (h1, h2, h3), and in titles should be treated as more important than the other words. <em>Please, verify which are the relevant HTML tags to select the important words.</em></li>

</ul>

<h2>Search</h2>

Your program should prompt the user for a query. <strong>This doesn’t need to be a Web interface, it can be a console prompt</strong>. At the time of the query, your program will stem the query terms, look up your index, perform some calculations (see ranking below) and give out the ranked list of pages that are relevant for the query, with the most relevant on top. Pages should be identified <strong>at least </strong>by their URLs (but you can use more informative representations).

<ul>

 <li><strong>Ranking</strong>: at the very least, your ranking formula should include tf-idf, and consider the important words, but you are free to add additional components to this formula if you think they improve the retrieval.</li>

</ul>

<h2>Extra Credit</h2>

Extra credit will be given for tasks that improve the quality of the retrieval and of the user search experience. For example:

<ul>

 <li>Detect and eliminate duplicate pages. (1 point for exact, 2 points for near) • Implement Page Rank, and use it in your ranking formula. (3 points)</li>

 <li>Implement an additional 2-gram and/or 3-gram indexing and use it during retrieval. (2 points)</li>

 <li>Enhance the index with word positions and use that information for retrieval. (2 points)</li>

 <li>Index anchor words for the target pages (1 point).</li>

 <li>Implement a Web or GUI interface instead of using the console. (2 points for the local GUI, 3 points for a web GUI)</li>

</ul>

<h1>Additional Specifications for Information Analyst</h1>

Option available to all groups formed only by non-CS and non-SE students.

<strong>Programming skills required</strong>

Intro courses.

<h2>Main challenges</h2>

HTML and JSON parsing, read/write structured information from/to files or databases.

<strong>Corpus</strong>

A small portion of the ICS web pages (analyst.zip).

<h2>Indexer</h2>

You can use a database to store the index, or a simple file – whatever is simpler to you. If you store it in a file, the index is expected to be sufficiently small, so that it fits in memory all at once.

<strong>Search interface</strong>

The response to search queries should be less than 2 seconds.

<h2>Note</h2>

This project can be a great addition to your r´esum´e and job interviews:

<ul>

 <li><strong>Tired</strong>: “Wrote a Python script that finds words in Web pages.”</li>

 <li><strong>Wired</strong>: “Wrote a search engine from the ground up that is capable of handling two thousand documents or Web pages.”</li>

</ul>

<h1>Additional Specifications for Algorithms and Data Structures Developer</h1>

Option available to all students, but required for CS and SE students.

<strong>Programming skills required</strong>

Advanced.

<h2>Main challenges</h2>

Design efficient data structures, devise efficient file access, balance memory usage and response time.

<strong>Corpus</strong>

A large collection of ICS web pages (developer.zip).

<strong>Indexer</strong>

Your index should be stored in one or more files in the file system (no databases!).

<h2>Search interface</h2>

The response to search queries should ≤ 300ms. Ideally it would be . 100ms, but you won’t be penalized if it’s higher (as long as it’s kept ≤ 300ms).

<h2>Operational constraints</h2>

Typically, the cloud servers/VMs/containers that run search engines don’t have a lot of memory. As such, you must design and implement your programs as if you are dealing with very large amounts of data, so large that you cannot hold the inverted index all in memory. Your indexer must off load the inverted index hash map from main memory to a partial index on disk at least 3 times during index construction; those partial indexes should be merged in the end. Optionally, after or during merging, they can also be split into separate index files with term ranges. Similarly, your search component must not load the entire inverted index in main memory. Instead, it must read the postings from the index(es) files on disk. <strong>The TAs will verify that this is happening.</strong>

<h2>Note</h2>

This project is a great addition to your r´esum´e and job interviews:

<ul>

 <li><strong>Tired</strong>: “Wrote a Web search engine using ElasticSearch.”</li>

 <li><strong>Wired</strong>: “Wrote a search engine from the ground up that is capable of handling tens of thousands of documents or Web pages, under harsh operational constriants and having a query response time under 300ms.”</li>

</ul>




<h1>Milestone 1</h1>

<strong>Goal</strong>: Build an index

<h2>Building the inverted index</h2>

Now that you have been provided the HTML files to index, you may build your inverted index off of them. The inverted index is simply a map with the token as a key and a list of its corresponding postings. A posting is the representation of the token’s occurrence in a document. The posting typically (not limited to) contains the following info (you are encouraged to think of other attributes that you could add to the index):

<ul>

 <li>The document name/id the token was found in.</li>

 <li>Its tf-idf score for that document.</li>

</ul>

Some tips:

<ul>

 <li>When designing your inverted index, you will think about the structure of your posting first.</li>

 <li>You would normally begin by implementing the code to calculate/fetch the elements which will constitute your posting.</li>

 <li>Use scripts/classes that will perform a function or a set of closely related functions. This helps in keeping track of your progress, debugging, and also dividing work amongst teammates if you’re in a group.</li>

 <li>We recommend you use GitHub as a mechanism to work with your team members on this project, but you are not required to do so.</li>

</ul>

<h2>Deliverables</h2>

Submit a report (pdf) to with the following content:

<ul>

 <li>a table with assorted numbers pertaining to your index. It should have, at least the number of documents, the number of [unique] tokens, and the total size (in KB) of your index on disk.</li>

</ul>

<strong>Note for the developer option</strong>: at this time, <em>you do not need </em>to have the optimized index, but you may save time if you do.

<strong>Evaluation criteria</strong>

<ul>

 <li>Did your report show up on time?</li>

 <li>Are the reported numbers plausible?</li>

</ul>

<h1>Milestone 2</h1>

<strong>Goal</strong>: Develop a search and retrieval component

At least the following queries should be used to test your retrieval:

<ul>

 <li>cristina lopes</li>

 <li>machine learning</li>

 <li>ACM</li>

 <li>master of software engineering</li>

</ul>

<h2>Developing the Search component</h2>

Once you have built the inverted index, you are ready to test document retrieval with queries. At the very least, the search should be able to deal with boolean queries: AND only.

If you wish, you can sort the retrieved documents based on tf-idf scoring (you are not required to do so now, but doing it now may save you time in the future). This can be done using the cosine similarity method. Feel free to use a library to compute cosine similarity once you have the term frequencies and inverse document frequencies. You may also add other weighting/scoring mechanisms to help refine the search results.

<h2>Deliverables</h2>

Submit a report (pdf) to with the following content:

<ul>

 <li>the top 5 URLs for each of the queries above</li>

 <li>a picture of your search interface in action</li>

</ul>

<strong>Note for the developer option</strong>: at this time, <em>you do not need </em>to have the optimized index, but you may save time if you do.

<h2>Evaluation criteria</h2>

<ul>

 <li>Did your report show up on time?</li>

 <li>Are the reported URLs plausible?</li>

</ul>

<h1>Milestone 3</h1>

<strong>Goal</strong>: Develop a complete search engine

During this last stretch, you will improve and finalize your search engine.

Come up with a set of at least 20 queries that guide you in evaluating how well your search engine performs, both in terms of ranking performance (effectiveness) and in terms of runtime performance (efficiency). At least half of those queries should be chosen because they do poorly on one or both criteria; the other half should do well. Then change your code to make it work better for the queries that perform poorly, while preserving the good performance of the other ones, and while being as general as possible.

<h2>Deliverables</h2>

<ul>

 <li>Submit a zip file containing all the programs you wrote for this project, as well as a document with your test queries (no need to report the results). Comment on which ones started by doing poorly and explain what you did to make them perform better.</li>

 <li>A live demonstration of your search engine for the TAs.</li>

</ul>

<h2>Evaluation criteria</h2>

<ul>

 <li>Does your search engine work as expected of search engines?</li>

 <li>How general are the heuristics that you employed to improve the retrieval?</li>

 <li>Is the search response time under the expected limit?</li>

 <li>Do you demonstrate in-depth knowledge of how your search engine works? Are you able to answer detailed questions pertaining to any aspect of its implementation?</li>

</ul>

<strong>Note for the developer option</strong>: at the end of the project, you should have the optimized index that allows you to run both the indexer and the search with small memory footprint, smaller than the index size.




<h1>Understanding the dataset</h1>

In Assignment 2, your crawlers crawled the many web sites associated with ICS. To avoid you need to crawl again and save you some time, we collected a chunk of these pages and are providing them to you.

<h2>Data files</h2>

There are two zip files: <strong>analyst.zip </strong>and <strong>developer.zip</strong>. The names should be self-explanatory: the former is for the analyst flavor of the project; the latter is for the algorithms and data structures developer option. The only difference between them is the size: analyst.zip contains only 3 domains<a href="#_ftn1" name="_ftnref1"><sup>[1]</sup></a> and a little over 2,000 pages, while developer.zip contains 88 domains and little under 56,000 pages. The following is an explanation of how the data is organized.

<strong>Folders</strong>: There is one folder per domain. Each JSON file inside a folder corresponds to one web page.

<strong>Files</strong>: The files are stored in JSON format, with 2 fields:

<ul>

 <li><strong>url</strong>: contains the URL of the page. Ignore the fragment parts, if you see them around.</li>

 <li><strong>content</strong>: contains the content of the page, as found during crawling</li>

 <li><strong>encoding</strong>: and indication of the encoding of the webpage.</li>

</ul>

<h2>Broken or missing HTML</h2>

Real HTML pages found out there are full of bugs. Some of the pages in the dataset may not contain any HTML at all and, when they do, it may not be well formed. For example, there might be an open &lt;strong&gt; tag but the associated closing &lt;/strong&gt; tag might be missing. While selecting the parser library for your project, please <em>ensure </em>that it can handle broken HTML.

<a href="#_ftnref1" name="_ftn1">[1]</a> <em>Domains</em>, for the purposes of this project.