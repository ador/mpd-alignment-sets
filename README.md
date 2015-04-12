
This repository contains selected alignment datasets from OXBench,
used in *"Efficient representation of uncertainty in multiple sequence alignments using directed acyclic graphs"*
by Joseph L Herman, Ádám Novák, Rune Lyngsø, Adrienn Szabó, István Miklós and Jotun Hein. (2014)

### Data selection procedure

1. Selecting a large reference alignment
From [OXBench version 1.3](http://www.compbio.dundee.ac.uk/downloads/oxbench/oxbench_1_3.tar.gz)
one of the largest alignments was chosen, which was dataset number 12.
(After unpacking the tar.gz file above, it can be found in: "oxbench_1_3/data/align/fasta/12" )
It contains 122 protein sequences.
2. Selecting diverse subsets of growing sizes
So that we can conduct measurements of running times of our method, and be less affected
by different characteristics of alignments, we chose to select subsets of the same protein family.
To avoid having too highly similar proteins in a subset, we used a simple algorithm
to choose a maximally dissimilar protein (least similar to the already selected ones) in each round.
We run this greedy algorithm to produce protein subsets of the *12* set of sizes: 15, 30, 60; and 
also included the full set of 122 sequences in our measurement dataset. This way the respective 
sizes of subsets (almost) double, which makes drawing consequences of measures running times easier.
3. All-gap columns have to be removed
In order to get valid sub-alignments, we removed the alignment columns that contained gaps only.


### Results

The final subsets that we selected contain 15, 30, 60 and 122 sequences respectively.
The larger ones always include all protein sequences from the smaller subsets and extend 
them further.
![Subsets containing each other](img/subsets.png?raw=true)

To find the alignments have a look at the "data" folder.

