<h1>Word2Vec</h1>
<h2>About Project:</h2>
<p>
  <img src='https://github.com/SurajChinna/Word2Vec/blob/master/assets/image1.png' />
</p>
  <h2>Word Embeddings</h2>
  <p>
    Word Embedding is just a vector representation of a word and words with similar meaning have nearly same representation. 
    Inorder to represent words, we generally use <b>One-Hot encoding</b>. In this technique, we will have a vector of dimension number 
    of words in the corpus or text which is filled with 0 except one location where we will have 1, which represents the word. 
    The disadvantage of this technique is we will have costly matrix multiplications which will result in mostly zero 
    valued hidden outputs. To solve this problem, we use <b>embeddings</b>.
    <br /><br />
    Embeddings are just a fully connected layer that is learnt and it's weights are called <b>embedding weights</b>. We skip the 
    multiplication into the embedding layer by instead directly grabbing the hidden layer values from the weight matrix. Why?? 
    We can do this because the multiplication of a one-hot encoded vector with a matrix returns the row of the matrix corresponding
    the index of the input unit.
    <br /><br />
    Instead of doing the matrix multiplication, we use the weight matrix as a lookup table. We encode the words as integers, 
    for example "heart" is encoded as 958, "mind" as 18094. Then to get hidden layer values for "heart", you just take the 958th 
    row of the embedding matrix. This process is called an <b>embedding lookup</b> and the number of hidden units is the 
    <b>embedding dimension</b>.
    <br /><br />
    There is nothing magical going on here. The embedding lookup table is just a weight matrix. The embedding layer is just a 
    hidden layer. The lookup is just a shortcut for the matrix multiplication. The lookup table is trained just like any weight matrix.
  </p>
  <h2>Word2Vec</h2>
  <p>
    Word2Vec is a statistical method for efficiently learning a word embedding from a text corpus. The Word2Vec algorithm finds much more 
    efficient representations by finding vectors that represent the words. These vectors also contain semantic information about the words.
    <br /><br />
    Words that show up in similar contexts, such as "coffee", "tea", and "water" will have vectors near each other. Different words 
    will be further away from one another, and relationships can be represented by distance in vector space.
    <br /><br />
    There are two architectures for implementing Word2Vec:
    <ol>
      <li>CBOW (Continuous Bag-Of-Words)</li>
      <li>Skip-Gram</li>
    </ol>
  </p>
    <h3>1. CBOW (Continuous Bag-Of-Words):</h3>
    <p>
    The embedding is learnt by predicting the current word based on its context.
    <br />
    <img src="https://github.com/SurajChinna/Word2Vec/blob/master/assets/image2.png">
    <br /><br />
    <h3>2. Skip-Gram</h3>
    Skip Gram model learns by predicting the surrounding words given a current word
    <br />
    <img src="https://github.com/SurajChinna/Word2Vec/blob/master/assets/image3.png">
    Both CBOW and Skip-Gram has its own pros and cons, but Skip-Gram generally performs well. So, we will implement Skip-Gram.
    To see the implementation of the Skip-Gram, go to Skip-Gram.ipynb notebook or 
    <a href="https://github.com/SurajChinna/Word2Vec/blob/master/Skip%20Gram.ipynb">click here</a> 
    </p>
  
