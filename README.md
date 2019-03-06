# Language model N-gram

## Table Of Contents
  **[Documentation](#documentation)**<br>
  **[Applications](#applications)**<br>
  **[Reasions](#reasions)**<br>
### Documentation
  1. [N-gram Language Models](https://web.stanford.edu/~jurafsky/slp3/3.pdf)
  2. [Modeling Natural Language with N-Gram Models](https://sookocheff.com/post/nlp/n-gram-modeling/)
  3. [N-Gram Language Models Explained with Examples](https://vitalflux.com/n-gram-language-models-explained-examples/)
  4. [N-gram-language models](http://www.cis.hut.fi/Opinnot/T-61.281/Luennot08/luento08_9.pdf)
  5. [N-gram Language Modeling Tutorial](http://ssli.ee.washington.edu/WS07/notes/ngrams.pdf)
  6. [Big exercise](https://www.slideshare.net/kimdinhsonict/ngram-29611724)
  7. [Edit fomula in mydocument](http://latex.codecogs.com/eqneditor/editor.php)
### Applications
  * automated machine translation
  * predict the next most likely word to occur in a sentence
  * automatically generate text from speech
  * automate spelling correction
  * determine the relative sentiment of a piece of text
### Reasions
  * identify words in noisy, ambiguous input, like speech recognition or handwriting recognition
  * cho biết phân bố xác xuất trên các tập văn bản là bao nhiêu
### Công Thức Tính Xác Suất
  1. Công thức Bayes: <br>
  * ![Công thức Bayes](http://latex.codecogs.com/gif.latex?P%28AB%29%3DP%28B%7CA%29*P%28A%29)
  * ![Công thức Bayes cho chuỗi W](http://latex.codecogs.com/gif.latex?P%28W_%7B1%7DW_%7B2%7D..W_%7Bm%7D%29%3DP%28W_%7B1%7D%29*P%28W_%7B2%7D%7CW_1%29*P%28W_%7B3%7D%7CW_%7B1%7D%5E%7B2%7D%29*...*P%28W_m%7CW_%7B1%7D%5E%7Bm-1%7D%29)
  2. Xấp xỉ Markov:<br>
  * ![Công thức Markov](http://latex.codecogs.com/gif.latex?P%28W_%7B1%7DW_%7B2%7D..W%7Bm%7D%29%20%3D%20P%28W_%7B1%7D%29*P%28W_%7B2%7D%7CW_%7B1%7D%29*P%28%7BW_%7B3%7D%7CW_%7B1%7D%5E2%7D%29..*P%28W_%7Bm%7D%7CW_%7Bm-n%7D%5E%7Bm-1%7D%29)
### Các N-Gram phổ biến
  1. Unigram
  2. Bigram
  3. Trigram
### Các Phương pháp làm mịn
  1. Chiếc khấu (Discounting)
    * Add-one:
      - ![Tính Ci* với unigram](http://latex.codecogs.com/gif.latex?C_%7Bi%7D%5E*%20%3D%20%28C_%7Bi%7D&plus;1%29%5Cfrac%7BM%7D%7BM%5E%7B%27%7D%7D)  
      - ![Tính Pi* với unigram](http://latex.codecogs.com/gif.latex?P_%7Bi%7D%5E%7B*%7D%3D%5Cfrac%7BC_%7Bi%7D%5E%7B*%7D%7D%7BM%5E%7B%27%7D%7D%3D%5Cfrac%7BC_%7Bi%7D&plus;1%7D%7BM&plus;V%7D)<br>
      - ![Tính Pi* với ngram](http://latex.codecogs.com/gif.latex?P_%7Bi%7D%5E%7B*%7D%28W_%7Bi%7D%7CW_%7Bi-n&plus;1%7D%5E%7Bi-1%7D%29%3D%5Cfrac%7BC%28W_%7Bi-n&plus;1%7D%5E%7Bi%7D%29%7D%7BC%28W_%7Bi-n&plus;1%7D%5E%7Bi-1%7D%29&plus;V%7D)<br>
    * Writen-Bell
      - ![Tính P khi Ci-1=0](http://latex.codecogs.com/gif.latex?P%28W_%7Bi%7D%7CW_%7Bi-n&plus;1%7D%5E%7Bi-1%7D%29%3D%5Cfrac%7BT%28W_%7Bi&plus;n-1%7D%5E%7Bi%7D%29&plus;1%7D%7BZ%28W_%7Bi&plus;n-1%7D%5E%7Bi%7D%29%5BC%28W_%7Bi&plus;n-1%7D%5E%7Bi-1%7D%29&plus;T%28W_%7Bi&plus;n-1%7D%5E%7Bi%7D%29%5D%7D)
      - ![Tính P khi ci-1>0](http://latex.codecogs.com/gif.latex?P%28W_%7Bi%7D%7CW_%7Bi-n&plus;1%7D%5E%7Bi-1%7D%29%3D%5Cfrac%7BC%28W_%7Bi&plus;n-1%7D%5E%7Bi%7D%29&plus;1%7D%7BC%28W_%7Bi&plus;n-1%7D%5E%7Bi-1%7D%29&plus;T%28W_%7Bi&plus;n-1%7D%5E%7Bi%7D%29%7D)
    * Good - turing
  2. Truy hồi (Back-off)
  3. Nội suy (Interpolation)
