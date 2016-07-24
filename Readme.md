This is the Prophet tool mentioned on places on **[www.cs.miami.edu](http://www.cs.miami.edu/~tptp/ATPSystems/Prophet/)** , and in this  research paper by Aman Kakkad (addys06@gmail.com) who is a master's student at University of Miami [Machine Learning for Automated Theorem Proving](http://scholarlyrepository.miami.edu/cgi/viewcontent.cgi?article=1222&context=oa_theses).

Mentions of this tools can also be found in [Lemma Management Techniques for Automated Theorem Proving](http://www.cs.miami.edu/home/geoff/Papers/Conference/2005_ZS05_IWIL-5-87-94.pdf), and [Machine Learning for Automated Reasoning](http://www.cs.miami.edu/home/geoff/ResearchProjects/ForStudents/MLAR.pdf).


I had greate trouble in finding this tool, therefore I am uploading this so that it can help others. The original link for this tool is [ServiceTools](http://www.cs.miami.edu/~tptp/ServiceTools.tgz). It is listed on [this](http://www.cs.miami.edu/~tptp/) web page.

## User Guide from it's original web page
---

>Prophet
>Designed and Implemented by Yury Puzis
>
>Prophet is a tool that estimates the relevance of each axiom in a set, to (proving) a given conjecture. This relevance measure is based on the intuitive notion of whether or not formulae are "talking about the same things". In more concrete terms, this is measured in terms of the extent to which the formulae use the same predicate and function symbols.
>
>Prophet is implemented in C++, and can be used online through the SystemB4TPTP interface.
>
>Prophet has lots of options! ...
>
>SYNOPSIS
>    prophet -p FILE [options]
>
>OPTIONS
>        -p FILE        compute relevance for formulas in FILE
>
>      Direct relevance related
>        -d         direct relevance measure
>                   union    intersection of symbols / union of symbols
>                   [source]    intersection of symbols / symbols in source formula
>        -w         weight of a symbol (or a variable)
>                   trivial       1
>                   [formula]       1 - (# of formulae with the symbol / # of formulae)
>                   global        1 - (total occurrence of the symbol / # of symbols)
>                   flog        - log10(# of formulae with the symbol / # of formulae)
>        -v         handling of the variables (for direct relevance)
>                   note: existential variables are converted to universal
>                   [ignore]    disregard variables altogether
>                   unique    universal variables are unique
>                   similar    universal variables are similar to one another
>
>	Indirect relevance related
>        	-s          handling of functors and predicates relationship
>        	          [join]    use together
>        	          split    use separately, combine final scores
>        	          merge    use separately, merge direct relevance (on maximum)
>          -i XYZ        indirect relevance measure methods
>         				X:         estimating path length (p)
>         				Y:         calculating relevance based on a path (d)
>         				Z:         combining predicate and functor relevance value (t)
> 	Clustering related
>   				-n INTEGER    number of desired clusters (final might be smaller)
>   				-c        clustering method
>     					indirect    use isodata algorithm on final (indirect) relevances
>     					[direct]    finds fuzzy maximal cliques from direct relevance values
>	Debugging  
>			-g STRING    list of solution formulae names separated by space
>			-TEXT        output debugging information (text)
>			-GRAPH        generate graph of relevance (DOT format)
>			-FULLG          generate links between nodes in the same cluster
>   					clustered: dot -Tgif agraph.dot -o agraph.gif
>   					symmetric: neato -Gpack -Tgif agraph.dot -o agraph.gif
>TEMPLATES
>    	The following combinations of possible options are merely examples of how prophet can be used. They are ordered by efficiency (as shown in> empirical experiments). The topmost variant is the default.
>     	add < -p FILE > to every example to make it work.
>
>Name            Call
>default         -d source -w formula -v ignore -s join -i kdt -n 7 -c direct
>simple          -d union -w trivial -v ignore -s split -i ppt -n 7 -c indirect
>
> AUTHOR                                                                                                                                                                                                                                             > Yury Puzis (C) 2004 and the ART team
>

Hope it helps!
