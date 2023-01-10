# mfinder1.2-python
This notebook is python wrapper of network motif analyzer mfinder1.2(Milo et al. Science 2002). 
It has codes for the following steps and link them as a pipleline to analyze motif (subgraph) from network.

- Read graph from dictionary of NetworkX graph objects(.pkl) or directory containg graph files (/.gexf)

- **Run mfinder1.2** on the graph data : this analyzes numbers in real/randomized network, z-score for each motif id

- Compute **signifcance profile(SP; normalized z-score)** based on mfinder1.2 result for each motif id

- Write result of step 2. and step 3. as csv(.csv) file

- Visualize significance profile of the network using pyplot


## Reference 
Every resources of directory mfinder1.2 references following work of Milo R. et al.

https://www.weizmann.ac.il/mcb/UriAlon/download/network-motif-software

Milo R, Shen-Orr S, Itzkovitz S, Kashtan N, Chklovskii D, Alon U. Network motifs: simple building blocks of complex networks. Science. 2002 Oct 25;298(5594):824-7. doi: 10.1126/science.298.5594.824. PMID: 12399590.

## Dependencies 
- networkx
- numpy
- pandas
- pickle
- os
- subprocess

## Descriptions
- **src/mfinder_python.ipynb**
  - main wrapper notebook

- **mfinder1.2**
  - clone of original mfinder1.2 (https://www.weizmann.ac.il/mcb/UriAlon/download/network-motif-software)
  - mfinder1.2/mfinderManual.pdf
    - Please refer to this manual about input/output format, arguement options and other details about mfinder program.
  - mfinder1.2/motifDictionary
    - Please refer to this dictionary about various motif structures and their id
    
- **data**
  - inputs should be manually placed here under dataset directory as **data/[my_dataset_name]/[my_inputs]**. There are 2 options of input file format. Please refer to **src/mfinder_python.ipynb** for details.
  - **option 1. dictionary of NetworkX graph objects** : data/[my_dataset_name]/[my_dictionary_name].pkl
  - **option 2. directory of .gexf files** : data/[my_dataset_name]/gexf/[my_gexf_name].gexf
  
- **input**
  - intermediate .txt files, which are automatically generated and is used as input for mfinder1.2.exe, are placed here. 
  - You could either automatically write input files starting from files in **data/[my_dataset_name]** directory, or manually write .txt input files matching the input format of mfinder1.2 here.

- **output**
  - all the results including followings are generated here.
  - [file_name]_OUT.txt : mfinder1.2.exe's raw output file. You may refer to this files for overview of each analysis results
  - [file_name].jpg : single visualization of motif significance profile(SP) of all the indexed graphs. Please refer to section **[Visualize Motif significance profile]** of **src/mfinder_python.ipynb** for deatils. 
  
    
