Introduction
MGST  implements a genome-scale algorithm: Maximum Gene-Support Tree (MGST) to estimate species tree from multiple gene trees based on multilocus sequences. It provides a new option for multiple genes to infer species tree. It is incorporated into popular phylogentic program: PHYLIP package with the same usage and user interface. It is suitable for phylogenetic methods including not only Baysian, but also maximum parsimony, maximum likelihood, neighbour-joining and so on. These methods are used to reconstruct single gene trees separately firstly with a variety of phylogenetic inference programs, then infer a species from multiple gene trees. Statistical confidence tests: chi-square test and Likelihood ratio G test are available for determining statistical significant level between the maximum gene support and the most second or third gene support. 
________________________________________
Get MGST
MGST is distributed under GNU Public License (GPL). All its source codes are freely available to both academic and commercial users. The latest version (version 1.2)  can be downloaded at theGITHUB download page. 
________________________________________
Install MGST
You could compile MGST with: 
make all
or 
 make MGSTT

However, executable version is included.
IMPORTANT NOTE: 
 MGSTT new version start from a tree file with all trees in newick format,  the usage and user interface is same as the  treedist program in PHYLIP package, while old version from a tree distance matrix by PAUP, PHYLIP, Mr.Bayes or others already.
Use MGST 
1. new version: gsupport 1.2
Input files: intree, a tree file in Tree Newick format:
(Shark,Teleost,(Human,(Coelacanth,Lungfish)));
./gsupport
Fellow the prompts and type your input.
Type D, return  choose Symmetric Distance
Type 2,  return then type P  return for all possible pair tree comparisons
Type F, return  for Full Matrix
Type Y,  return for confirming your settings
Example 1 in example fold:
a. input file: intree like following.
((Coelacanth:0.09871,Shark:0.12766):0.00662,Lungfish:0.08105,Amphibian:0.12522);
(Shark:0.10643,(Coelacanth:0.02857,Lungfish:0.06285):0.01701,Amphibian:0.02588);
(Shark:0.00010,(Coelacanth:0.00591,Lungfish:0.03833):0.00610,Amphibian:0.02364);
...

b. Output files: Outfile (tree distances matrix)
0  2  4   
2  0  4  
4  4  0  

c. treeFrq.txt (Tree frequences)
Frequency of trees: 
    5
    3
    2
    1
    1
...
d. treeId.txt ( Tree serial No in tree distance matrix)
Tree series ID:
    1    2    3    4    5
    6    7    8
    9   10
   11
   12
   13
   14
   15
   16
   17
f. ChiTestResults.txt ( Chi Square Test output)
Tree pair chi-square values:
 0.000    0.750    3.125    12.250   
 0.800    0.083    0.125    2.250   
 1.800    0.750    0.125    0.250   
 3.200    2.083    1.125    0.250   

Other Perl Scripting to extract all trees from all files in the fold and create a file with all trees.
Perl: Parse_tree_files_fold.pl

2.  version 1.1b;

Compiling: gcc -lm MGST_td.c  -o MGST_td
However, executable version is included.
This is suitable when  tree distance matrix has  been calculated by PAUP, Phylip or other programs.

 Input file: full matrix of tree distances without any labels (Column names and row names).

./MGST_td

Following prompts to type your information.

Example:

a. input files: infile.txt (tree distances matrix, it is the output file from treedist program such as Phylip, PAUP , )
Notes: no column names and row names  in matrix like following.

0  2  4   
2  0  4  
4  4  0  

The following steps are same as above in new version.
b. treeFrq.txt (Tree frequences)
Frequency of trees: 
    5
    3
    2
    1
    1
    1
    1
    1
    1
    1
c. treeId.txt ( Tree serial No in tree distance matrix)
Tree series ID:
    1    2    3    4    5
    6    7    8
    9   10
   11
   12
   13
   14
   15
   16
   17
d. ChiTestResults.txt ( Chi-Square Test output)
Tree pair chi-square values:
 0.000    0.750    3.125    12.250   
 0.800    0.083    0.125    2.250   
 1.800    0.750    0.125    0.250   
 3.200    2.083    1.125    0.250   
Questions:  Please forward to henry.shan@gmail.com

Citation:
If you use this program, the following reference is available.
Yunfeng Shan and Xiu-Qing Li (2008) Maximum Gene-support Tree:  Evolutionary Bioinformatics, 4, 181-189.
