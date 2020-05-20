# 第 15 章：也许为真——但你无法证明！

本章标题听上去像是小毛贼可能对警察说的话。但实际上，它宣称了过去100年里逻辑学中另一个最重要的结果。（快速警告：前面的章节中我使用了小写字母 ($$a,b$$ 等等) 表示语句。本章我将使用大写字母($$A,B$$ 等等)表示语句，以避免任何可能与数字的混淆。）

莱布尼茨不是逻辑学史上唯一有雄心壮志计划的逻辑学家。另一个人物是20世纪最重要的数学家之一，大卫·希尔伯特（David Hilbert，1862-1943），生活和工作于哥廷根。其计划通常称作**数学基础的希尔伯特纲领**（Hilbert Program in the Foundations of Mathematics），该纲领试图证明数学是一致的，即证明在数学中永远不会证明形如 $$A$$ 且$$\neg A$$ 的东西。1920年代，数学家仍然处于发现罗素悖论（我们在第5章见过）及其他同类悖论带来的震惊之中。这类悖论冲击到数学最核心的部分。希尔伯特想确保这种事情以后再也不会发生。

我们在这里要稍微小心一点。对一致性的证明当然也是数学证明。若数学是不一致的，或许它终究可以证明其一致性。事实上，若使用的逻辑是我们在第2章中见过的那种，若数学是不一致的，则它能证明一切！正如我们在那里见到的，在这种逻辑中，任何命题都可以从矛盾中得出。因此，对一致性的证明必须在某种特别安全的数学推理中完成。希尔伯特称这种推理为**有穷的**（finitary）。不过这与我们要讲的内容并不相关。

有关的是下面这些。要证明某个东西是一致的，你首先要对它有个确切的了解。如果你要运用数学证明它，你要对数学有个精确的界定。因此，作为其主要主要纲领的预备步骤，希尔伯特需要为数学提供一个恰当的公理系统，从而证明其一致性。

一个公理系统由一组**公理**（axioms）构成。公理是无需证明即可被接受的东西。（公理集可以是有穷的，也可以是无穷的。但如果是无穷的，则我们要能识别某个东西是不是公理。具体而言，需要有一个算法来判定这件事。）该系统中的一个**证明**（proof），就是一个陈述序列，其中每个陈述要么是一条公理，要么可以从前面的陈述通过推演得到。该系统的**定理**（throrems），就是每个证明最末尾的陈述。于是，定理就是从公理出发，最终能推演得到的东西。

公理化方法是数学中的一个古老方法。它被古希腊数学家欧几里得（Euclid，公元前 4 世纪中叶至 3 世纪中叶）应用于几何。不过，有点奇怪的是，直到 20 世纪，该方法才在数学中被广泛应用。在此之前，数学中被公理刻画的部分，就只有几何（或者更准确地说，是各种几何；19世纪初，数学家已经知道除了欧几里得几何之外的其他几何——非欧几何）和抽象代数的某些部分。

希尔伯特的宏伟计划则要求所有数学都被公理化。即，我们需要一个公理系统，其所有定理恰好是所有真的数学论断（无论人们如何理解数学中的真是什么）。这种公理系统的存在性，被或许是20世纪最著名的逻辑学家、奥地利数学家哥德尔（Kurt Gödel，1906-1978）反驳了。哥德尔表明，别说整个数学，就是对数学中关于自然数（0，1，2，…）的部分，也无法提供这样一种公理系统。数学中的这部分通常被称作**算术**（arithmetic）。因此，哥德尔证明的是，即使有公理系统可以刻画算术的*部分*真理，也没有公理系统可以刻画算术的全部真理。正如逻辑学家所说，该公理系统必定是**不完全的**（incomplete）。

有了我们在第14章学到的东西，哥德尔的结果就可以以相当直接的方式证明。证明仍然是归谬法。考虑一个能谈论数并能表达对数的操作（加、乘等）的符号语言。这种语言并不难得到。在该语言中可表达如下陈述：编码为$n$的程序输入 $$i$$ 后会终止。（要证明这一点需要费点功夫，但并不难。）称该陈述为 $$S_{ni}$$。现在假设存在一个完备的关于算术的公理系统，即一个其所有定理恰好是该语言中所有真陈述的公理系统。于是就存在一个判定 $$S_{ni}$$ 是否为真的算法：我们只要以一种系统的方式开始证明所有定理即可，确保任何可被证明的迟早被证明。（不难设计这样一个程序。）这样，迟早要么得到 $$S_{ni}$$ 的证明，要么得到 $$\neg S_{ni}$$ 的证明，从而判定上述问题。（我们可能不知道要多久才能完成，但这不重要）。但第 14 章的停机定理告诉我们，不存在一个算法能判定这件事。因此，不存在这样的公理系统。

我刚刚概述的证明并非哥德尔本人的证明。事实上，哥德尔的证明出现于 1931 年，而图灵证明停机定理是在 5 年之后。但哥德尔的证明和图灵的证明一样精巧——如果说不是更精巧的话——而且也使用了某种自指。哥德尔证明的概要如下。

假设我们在有一个其语言有足够表达能力的算术公理系统。该系统的所有定理都为真，但它可能无法证明该语言中**所有**真的陈述，因此它可能是不完全的。该语言的一个数学陈述就是一段文本。正如我们在第 14 章指出的，这样的陈述可以被编码为一个数。一个计算机程序就是一个陈述序列，同样正如我们在第14章指出的，它也可以被编码为一个数。但一个数学证明也只是一个陈述序列，因而也可以以相同方式编码为一个数。

现在考虑这个陈述：$$x$$ 是编码为 $$y$$ 的陈述的证明（的编码）。该陈述本身是一个关于数的陈述，它可以表达为该语言中的一个语句 $$Prov(x,y)$$。并且，只要该系统的公理足够强，就有：

- 若 $$m$$ 的确是编码为 $$n$$ 的定理的证明（的编码），则 $$Prov(m,n)$$ 可在该公理系统中被证明。

要证明这些事情实际上相当难，需要一些可观的数学。但它可以做到，正如哥德尔所证明的。

说编码为 $$y$$ 的陈述是可证的，即是说它存在一个证明：$$\exists xProv(x,y)$$。但是——这是哥德尔证明的真正巧妙之处——通过一个精巧的构造，我们可以找到一个本质上形如 $$\neg\exists xProv(x,n)$$ 的语句，其编码恰好是 $$n$$ 本身！该陈述相当于说，本陈述（在系统中）不可证。称该语句为 $$G$$（代表哥德尔）。

现在，假设 $$G$$，即 $$\neg\exists xProv(x,n)$$，在该公理系统中是可证的。那就有个数 $$m$$ 是 $$G$$ 的某个证明的编码。这样，$$Prov(m,n)$$ 就为真，因而在公理系统中是可证的（根据上面的 $$\bullet$$）。但由此可得 $$\exists xProv(x,n)$$ 是可证的。于是该公理系统就是不一致的。假设系统要是一致的，则 $$G$$ 就是不可证的。但如此一来它就是真的，因为它恰好就是说它自己不可证！因此，该语言中有真的语句在系统中无法被证明。这样，算术就没有完全的公理系统。

哥德尔定理——无论它是如何证明的——明确表明了公理化方法在数学中的限度（这不是说公理化方法不应该被使用：事实上，如今公理化方法比以往任何时候都更加是数学方法的主要部分）。特别的，它给了希尔伯特纲领致命一击。算术无法被公理化——更不用说整个数学了。哥德尔的结果已被认为有很多哲学上的后果，包括关于数的本质，我们关于数的知识，甚至是人类心灵的本质。争论仍在继续，我们这里就不展开了。

让我再次以提出关于该定理的一个问题结束。我给的两个证明在数学上是无可辩驳的。但两个证明都做了一个假定（希尔伯特当然认为——或至少希望——它是成立的）：即关于数的真陈述，以及刻画其任何部分的公理系统是一致的。这在哥德尔的证明中是相当明确的假定，而我也在第一个证明中给出了。该证明假定 $$S_{ni}$$ 和 $$\neg S_{ni}$$ 中**恰好有一个**会出现，从而确定事情是如此还是那般。但如果系统是不一致的，这就不再成立：可能两个一起出现，使得事情悬而不决！

现在，正如有些读者可能看到的，哥德尔证明中使用的语句 $$G$$ 很像我们在第 5 章见过的说谎者悖论的表亲。两个都对某个语句，即它自己，说了它不具有某个关键性质。事实上，有一个关于可证性的悖论与说谎者悖论密切相关。考虑如下语句：**本语句不可证**。假设它是可证的，则它是真的。因而它是不可证的。因此（据归谬法），它不可能是可证的。但我们刚刚证明了这一点，因此它**是**可证的！

如果我们试图对语句 $$G$$ 在其公理系统中进行这种推理，则它无法在该系统中再现。或许令人惊讶的是，若系统是一致的，则可证的都是真的这一论断并不能在系统中得到证明。（这一点由德国数学家Martin Löb（1921-2006）在 1955 年证明，因而通常称作 **Löb定理**。）因此该悖论无法用于证明公理系统的不一致性。然而，它确实表明，自指悖论就藏在算术周围。考虑到这一点，人们或许不应该如此自信地认为，关于数的真理是一致的。

> 本章要点
>
> - 一个算术公理系统是完全的，若它能证明其语言中的所有真语句。
> - 没有其语言具有足够表达力的公理系统是完全的。
> - 该结论可由停机定理推出。
> - 它也可以通过考虑本质上相当于说本语句（在系统中）不可证这样的语句而证明。

尾声：哥德尔第二不完全性定理

本章我们考察的结果有时称作哥德尔**第一**不完全性定理。在证明这一结果的同时，哥德尔还证明了另一个结果，称作第二不完全性定理。它本质上表明了，如我我们有一个我们考察过的那种一致的公理系统，则它无法证明被认为表达了该系统一致性的语句——只要该系统是基于我们在第2章中看到的逻辑。事实上，有了 Löb 定理，可以很容易证明这一点。

首先，注意到既然系统能证明 $$\neg 0=1$$，那么若它还能证明 $$0=1$$，则它就是不一致的。反过来，若它是不一致的，则它能证明 $$0=1$$，因为从矛盾可以推出任何结论，这是我们在第 2 章中提到的。因此，系统是一致的一个简单说法是说它无法证明 $$0=1$$。

现在，设 $$A$$ 是该语言中的任何语句，记其编码为 $$\langle A\rangle$$ ，则 Löb 定理更精确一点的表述如下：

- 若系统能证明语句 $$\exists xProv(x,\langle A\rangle)\to A$$，则它也能证明语句 $$A$$。

即：

- 若系统无法证明语句 $$A$$，则它无法证明语句 $$\exists xProv(x,\langle A\rangle)\to A$$。

因此，作为特例，若它无法证明 $$0=1$$，则它无法证明：

- $$\exists xProv(x,\langle 0=1\rangle)\to 0=1$$

换言之，若它是一致的，则它无法证明 $$\exists xProv(x,\langle 0=1\rangle)\to 0=1$$。

但这样一来它就也无法证明 $$\neg\exists xProv(x,\langle 0=1\rangle)$$，因为无论 $$C$$ 是什么，$$A\to C$$ 都可以由 $$\neg A$$ 推出（如第 7 章中的真值表显示的，若 $$A$$ 为假，则 $$A\to C$$ 为真）。因此若系统是一致的，则它无法证明 $$\neg\exists xProv(x,\langle 0=1\rangle)$$，即（无法证明）它**是**一致的。这就是哥德尔第二不完全性定理。

该定理给了希尔伯特纲领第二个打击。回顾一下，该纲领的目标首先是公理化数学，然后其次是证明该公理系统是一致的。这样的证明当然是数学证明，因而在系统自身内可以实现。第一不完全性定理表明，纲领的第一步不可能实现。