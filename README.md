# 章岳——GEC论文

## A Comprehensive Survey of Grammar Error Correction

+ 链接：[ A Comprehensive Survey of Grammar Error Correction (arxiv.org)](https://arxiv.org/abs/2005.06600)

+ 简介：本文是南开大学几位本科生所撰写的GEC领域截止到2020年5月份的工作综述。本文主要从数据集、公开任务、标注细节、常用模型、常用性能提升方法、常用评测指标和数据增强方法等方面对GEC进行介绍。总体来说，描述得还算比较详细，涵盖了几乎所有GEC相关论文，但存在着一些公式等方面的错误。

## Parallel Iterative Edit Models for Local Sequence Transduction

+ 链接：[Parallel Iterative Edit Models for Local Sequence Transduction](https://www.aclweb.org/anthology/D19-1435.pdf)

+ 简介：本文提出了一种并行迭代编辑模型，用于解决局部序列转化类型的问题。局部序列转化问题，指的是目标序列与源序列仅在有限的几个位置有差异，常见的有：语法纠错、拼写纠正、OCR错误识别等。以GEC任务为例，当下的SoTA模型大都采用Seq2Seq的Encoder-Decoder架构神经机器翻译模型，但是存在着：1）自回归解码速度慢；2）需要大量训练数据；3）只有纠正结果，没有具体的错误类型等缺陷。作者在本文中首次提出了一种Seq2Edits的并行预测模型，将语法纠错任务看作是一种序列标注任务，使用Softmax分类器在源文本每个Token处预测一个编辑操作。同时，为了考虑各编辑操作之间的影响，使用了迭代纠正的方法。此外，作者还提出了几个对于模型结构的创新，使其更适合GEC任务。最终结果表明，本文提出的PIE模型的$F_{0.5}$指标和当前最佳的Seq2Seq模型类似，但是预测速度提升了5-15倍。
+ 解读博客：https://caoyang.blog.csdn.net/article/details/103674256

## GECToR -- Grammatical Error Correction: Tag, Not Rewrite

+ 链接：[GECToR -- Grammatical Error Correction: Tag, Not Rewrite (arxiv.org)](https://arxiv.org/abs/2005.12592)

+ 简介：这篇文章基本来说是当前GEC领域的SoTA了。本文由世界上最大的语法纠错软件Grammarly的研究人员发表。我认为这篇文章的创新性不大，模型的基本结构与PIE模型几乎类似，主要区别在于：1）设计了29种定制的g-transformation操作（即单独拎出来进行纠正的单复数变换、时态变换等）；2）将Fine-tuning阶段细分为了两个阶段：第一阶段使用含有错误的平行语料训练，第二阶段使用高质量的、错误句子和正确句子混合的平行语料训练；3）更换了新的预训练模型。个人认为，性能提升的最主要原因是因为本文使用了更加先进的预训练模型，如XLNet、RoBERTa等，而前人只使用BERT等。
+ 解读博客：http://fancyerii.github.io/2020/06/15/gector

## Seq2Edits: Sequence Transduction Using Span-level Edit Operations

+ 链接：[Seq2Edits: Sequence Transduction Using Span-level Edit Operations (arxiv.org)](https://arxiv.org/abs/2009.11136)

+ 简介：Seq2Edit的模型从2019年开始逐渐被人们用在局部序列转导任务上，例如：语法纠错、文本规范化等。但是，以往的Seq2Edit模型均为在Token级别预测并进行编辑操作，本文首次提出在Span级别预测并进行编辑。作者提出，在Span级别预测并进行编辑，能够利用更丰富的局部信息，更容易捕捉到Span内的依赖关系。作者为此提出了一个类多任务学习Transformer模型，自回归生成编辑序列$(t_n,p_n,r_n)$，其中：$t_n$表示当前编辑的标签Tag，$p_n$表示当前Span的结束位置Position，$r_n$表示用于替换从$p_{n-1}$到$p_n$的Span的字符串Replace。值得一提的是，作者在预测$p_n$时使用了Pointer NetWorks。由于生成编辑序列短于直接生成文本，所以本文模型比传统Text2Text的端到端GEC模型快2-5倍，同时，在多个LST任务上获得了SoTA效果。