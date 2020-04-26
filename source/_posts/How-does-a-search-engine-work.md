---
title: How Does A Search Engine Work?
date: 2017-04-04 22:45:37
tags: search
categories: Web

---
We use search engine every day, Google get 3 to 5 billions searching queries every day. I will give a brief introduction about how searching engine works.
<!-- more -->
## Documents as Vectors
When we get a list of documents, we need a specific way to define their relations between each other. Using a vector to present a document is a good way.
Suppose each document $j$ can be view as a vector of term frequency $tf$ values, then the dimension should be the number of all possible words, For example:
You have "documents", "as", "vectors" as the whole word space, then a document whose content is:

```
documents as vectors vectors vectors
```
will have a vector value of $(1,1,3)$.
It is easy to know the most documents are sparse vectors in real world.

Then we can also use a vector denotes a query, continue with the assumption above, a query of `vectors` will have a vector of: $(0,0,1)$

## TF $\times$ IDF Model
Among the universe of words, some words appear in almost every document like "the", "a", etc. Some words appear much less like "Rumpelstiltskin". It is intuitive to give different words distinct weights.
### Inverse-Document-Frequency
An easy way to describe the frequency of a word overall is to calculate its reciprocal expression：
$$
\frac{N}{n_k}
$$

 N is total number of documents and $n_k$ is the number of documents that contain term $T_k$
 We do some further mathematic operation and get the coefficient of term $T\_k$:
 $$
 C_{ik} = \log(\frac N{n_k})
 $$
... Comming soon


