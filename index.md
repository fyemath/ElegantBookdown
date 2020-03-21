--- 
title: "Elegant Bookdown Template"
subtitle: "优雅的 Bookdown 书籍模版"
author: 
  - 黄湘云
date: "2020-03-21"
site: bookdown::bookdown_site
documentclass: elegantbook
bibliography: 
 - book.bib
 - packages.bib
lot: yes
lof: yes
colorlinks: yes
toccolor: Maroon
link-citations: yes
mathspec: yes
subject: "基于 elegantbook 文类的 bookdown 模版"
keywords:
  - elegantbook
  - bookdown
  - pandoc
  - R
hyperrefoptions:
- linktoc=all
- pdfwindowui
- pdfpagemode=FullScreen
github-repo: XiangyunHuang/ElegantBookdown
classoption: "cn,11pt,chinese,bibstyle=apalike"
description: "最初看到 elegantbook 做的书籍样式很漂亮，就想把它引入到 bookdown 中，遂定制了此模版。在此基础上，做了迁移和扩展的工作，融合了 LaTeX (精美)、Pandoc (简洁) 和 R (强大) 的特性。This is a bookdown template based on ElegantBook. The output format for this template is bookdown::gitbook and bookdown::pdf_book."
---

\mainmatter

# 欢迎 {#welcome}



> A Markdown-formatted document should be publishable as-is, as plain text, without looking like it’s been marked up with tags or formatting instructions.  
> 
> --- John Gruber

这是一份 R Markodwn 文档。 Markdown 提供一种简洁的格式语法，支持数学公式 $\bm{\alpha}$（粗体）和 $\alpha$ （正常），用来生成 HTML、PDF 和 MS Word 文档。

当你点击 **Knit** 按钮时，就会生成一份包含正文和代码执行结果的文档。你可以像这样嵌入 R 代码块：


```r
summary(cars)
```

```
##      speed           dist       
##  Min.   : 4.0   Min.   :  2.00  
##  1st Qu.:12.0   1st Qu.: 26.00  
##  Median :15.0   Median : 36.00  
##  Mean   :15.4   Mean   : 42.98  
##  3rd Qu.:19.0   3rd Qu.: 56.00  
##  Max.   :25.0   Max.   :120.00
```

## 运行环境 {#session-info}


```r
xfun::session_info(c("rmarkdown", "bookdown", "knitr"), dependencies = FALSE)
```

```
## R version 3.6.2 (2017-01-27)
## Platform: x86_64-pc-linux-gnu (64-bit)
## Running under: Ubuntu 16.04.6 LTS
## 
## Locale:
##   LC_CTYPE=en_US.UTF-8       LC_NUMERIC=C              
##   LC_TIME=en_US.UTF-8        LC_COLLATE=en_US.UTF-8    
##   LC_MONETARY=en_US.UTF-8    LC_MESSAGES=en_US.UTF-8   
##   LC_PAPER=en_US.UTF-8       LC_NAME=C                 
##   LC_ADDRESS=C               LC_TELEPHONE=C            
##   LC_MEASUREMENT=en_US.UTF-8 LC_IDENTIFICATION=C       
## 
## Package version:
##   bookdown_0.18 knitr_1.28    rmarkdown_2.1
## 
## Pandoc version: 2.9.2
```





```r
ruler()
```

```
----+----1----+----2----+----3----+----4----+----5----+----6----+----
123456789012345678901234567890123456789012345678901234567890123456789
```

## Pandoc 

Pandoc 自诞生以来已历 15 个春秋，Github 星级 18.5k，而日常使用的 Hive 不过区区 3k。Pandoc 现已被各大 Linux 发行版（如 CentOS/Ubuntu 等）收录。下面给出一个使用 Pandoc 的简单例子

```bash
echo "hello, world!" > note.md
pandoc note.md -s -o note.tex # markdown 文本转化为 tex 文本
pandoc note.md -o note.pdf    # markdown 文本转化为 pdf 文档
pandoc note.md -o note.html   # markdown 文本转化为 html 文档
```

Pandoc 支持数十种文档输出格式，更多命令参数说明见 <https://pandoc.org/MANUAL.html>。可不可以不要 R，也不要 R Markdown 呢？当然可以，详见 <https://github.com/annProg/PanBook>，基于 Pandoc's Markdown 实现一次写作，多样输出！

## 各类 Block {#block}

\BeginKnitrBlock{lemma}<div class="lemma"><span class="lemma" id="lem:chf-pdf"><strong>(\#lem:chf-pdf) </strong></span>For any two random variables $X_1$, $X_2$, they both have the same probability distribution if and only if
$$\varphi _{X_1}(t)=\varphi _{X_2}(t)$$</div>\EndKnitrBlock{lemma}

\BeginKnitrBlock{theorem}<div class="theorem"><span class="theorem" id="thm:chf-sum"><strong>(\#thm:chf-sum) </strong></span>If $X_1$, ..., $X_n$ are independent random variables, and $a_1$, ..., $a_n$ are some constants, then the characteristic function of the linear combination $S_n=\sum_{i=1}^na_iX_i$ is
$$\varphi _{S_{n}}(t)=\prod_{i=1}^n\varphi _{X_i}(a_{i}t)=\varphi _{X_{1}}(a_{1}t)\cdots \varphi _{X_{n}}(a_{n}t)$$</div>\EndKnitrBlock{theorem}

\BeginKnitrBlock{proposition}<div class="proposition"><span class="proposition" id="prp:unnamed-chunk-5"><strong>(\#prp:unnamed-chunk-5) </strong></span>The distribution of the sum of independent Poisson random variables $X_i \sim \mathrm{Pois}(\lambda_i),\: i=1,2,\cdots,n$ is $\mathrm{Pois}(\sum_{i=1}^n\lambda_i)$.</div>\EndKnitrBlock{proposition}


\BeginKnitrBlock{proof}<div class="proof">\iffalse{} <span class="proof"><em>证明 </em></span>  \fi{}The characteristic function of $X\sim\mathrm{Pois}(\lambda)$ is $\varphi _{X}(t)=e^{\lambda (e^{it}-1)}$. Let $P_n=\sum_{i=1}^nX_i$. We know from Theorem \@ref(thm:chf-sum) that
\begin{equation*}
\begin{split}
\varphi _{P_{n}}(t) & =\prod_{i=1}^n\varphi _{X_i}(t) \\
& =\prod_{i=1}^n e^{\lambda_i (e^{it}-1)} \\
& = e^{\sum_{i=1}^n \lambda_i (e^{it}-1)}
\end{split}
\end{equation*}
This is the characteristic function of a Poisson random variable with the parameter $\lambda=\sum_{i=1}^n \lambda_i$. From Lemma \@ref(lem:chf-pdf), we know the distribution of $P_n$ is $\mathrm{Pois}(\sum_{i=1}^n\lambda_i)$.</div>\EndKnitrBlock{proof}

\BeginKnitrBlock{remark}<div class="remark">\iffalse{} <span class="remark"><em>注 </em></span>  \fi{}In some cases, it is very convenient and easy to figure out the distribution of the sum of independent random variables using characteristic functions.</div>\EndKnitrBlock{remark}


\BeginKnitrBlock{corollary}<div class="corollary"><span class="corollary" id="cor:unnamed-chunk-8"><strong>(\#cor:unnamed-chunk-8) </strong></span>The characteristic function of the sum of two independent random variables $X_1$ and $X_2$ is the product of characteristic functions of $X_1$ and $X_2$, i.e.,
$$\varphi _{X_1+X_2}(t)=\varphi _{X_1}(t) \varphi _{X_2}(t)$$</div>\EndKnitrBlock{corollary}

\BeginKnitrBlock{exercise}\iffalse{-91-67-104-97-114-97-99-116-101-114-105-115-116-105-99-32-70-117-110-99-116-105-111-110-32-111-102-32-116-104-101-32-83-97-109-112-108-101-32-77-101-97-110-93-}\fi{}<div class="exercise"><span class="exercise" id="exr:unnamed-chunk-9"><strong>(\#exr:unnamed-chunk-9)  \iffalse (Characteristic Function of the Sample Mean) \fi{} </strong></span>Let $\bar{X}=\sum_{i=1}^n \frac{1}{n} X_i$ be the sample mean of $n$ independent and identically distributed random variables, each with characteristic function $\varphi _{X}$. Compute the characteristic function of $\bar{X}$. </div>\EndKnitrBlock{exercise}

\BeginKnitrBlock{solution}<div class="solution">\iffalse{} <span class="solution"><em>解 </em></span>  \fi{}Applying Theorem \@ref(thm:chf-sum), we have
$$\varphi _{\bar{X}}(t)=\prod_{i=1}^n \varphi _{X_i}\left(\frac{t}{n}\right)=\left[\varphi _{X}\left(\frac{t}{n}\right)\right]^n.$$</div>\EndKnitrBlock{solution}

[要做的还有很多]{.todo}

::: rmdwarn
这是警告
:::

::: rmdtip
这是提示
:::

:::: rmdnote
这是注意
::::

::: sidebar
普通说明
:::


