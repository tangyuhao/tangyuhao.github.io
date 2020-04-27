---
title: How to Use Latex to Write Your Blog
tags: latex
categories: Technical Writing
---
To write math equations in my blog pages, I use Latex. Latex is a document preparation system which allows you to write professional-looking technical documents. For example, most of the scientific publications are written with Latex.
$$
Hello, \LaTeX\ world.
$$
The line above is created by adding a code block below in my markdown file (source files of blog pages):

```latex
$$
Hello, \LaTeX\ world.
$$
```
<!-- more -->

## Dependencies
You need to install some dependencies to make your hexo project be able to render "LaTex code" correctly in markdown files. For the [NexT theme](https://github.com/theme-next/hexo-theme-next) (the theme I use), you can easily find the "math" block and update it to to below:

```yml
math:
  enable: true
  # Default(true) will load mathjax/katex script on demand
  # That is it only render those page who has 'mathjax: true' in Front Matter.
  # If you set it to false, it will load mathjax/katex srcipt EVERY PAGE.
  per_page: false
  engine: mathjax
```

Besides, you need to make sure you have installed `hexo-renderer-kramed`:

```bash
npm install hexo-renderer-kramed --save
```

## Syntax
Here I list some basic syntax rules, you can find the full document in [LaTex Wikibooks](https://en.wikibooks.org/wiki/LaTeX).

### Escaping block
There are two ways to include $\LaTeX$ code in markdown:

1. use ` $<latex expression>$ ` to insert $inline$ expression;
2. use ` $$<latex expression>$$ ` to insert displayed expression:

$$I\ am\ a\ displayed\ expression!$$

### Alignment
You can use `&` to align different lines, and `\\` to add a line break.
```latex
\begin {aligned} 
A&=B \\
&=C \\
&=D 
\end {aligned}  
```
The rendered result is (note that I dismissed ` $$ `):

$$
\begin {aligned}
A&=B \\
&=C \\
&=D 
\end {aligned}  
$$



### Examples
Here are some math equations that we often use. 
#### Case block
```latex
sign(x)=
\begin {cases} 
+1, & x\geq0 \\
-1, & x<0 
\end {cases} 
```

$$ 
sign(x)=
\begin {cases} 
+1, & x\geq0 \\
-1, & x<0 
\end {cases} 
$$

#### Fraction
```latex
\frac{1}{1+e^{-x}}\\

\begin{aligned}
  x_0+\frac{1}{x_1+\frac{1}{x_2+\frac{1}{x_3+\frac{1}{x_4}}}}
\end{aligned}
```

$$\frac{1}{1+e^{-x}}\\
\begin{aligned}
  x_0+\frac{1}{x_1+\frac{1}{x_2+\frac{1}{x_3+\frac{1}{x_4}}}}
\end{aligned}
$$

#### Matrix

```latex
\begin{bmatrix} a & b \\ c & c \end{bmatrix}
\begin{vmatrix} x & y \\ z & v \end{vmatrix}
\begin{Bmatrix} x & y \\ z & v \end{Bmatrix}
\begin{pmatrix} x & y \\ z & v \end{pmatrix}
\begin{bmatrix} 0 & \cdots & 0 \\ \vdots & \ddots & \vdots \\ 0 & \cdots & 0 \end{bmatrix}
```

$$
\begin{bmatrix} a & b \\ c & c \end{bmatrix}
\begin{vmatrix} x & y \\ z & v \end{vmatrix}
\begin{Bmatrix} x & y \\ z & v \end{Bmatrix}
\begin{pmatrix} x & y \\ z & v \end{pmatrix}
\begin{bmatrix} 0 & \cdots & 0 \\ \vdots & \ddots & \vdots \\ 0 & \cdots & 0 \end{bmatrix}
$$




