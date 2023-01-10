MFINDER - README FILE
======================
mfinder is a software tool dedicated to find network motifs 
in complex networks.


COPYRIGHTS
===========
Nadav Kashtan, Shalev Itzkovitz, Ron Milo, Uri ALon 2002-2005. 

Version info
============

version : 1.2 
(Date : May 2005)


Platforms:
==========
Windows 2000,Windows XP.

For large and dense networks (more then 10000 nodes) it is
recommended to run mfinder on a computer with at least 
512 Mbyte RAM.

General
=======
mfinder can currently detect motifs of size 2-7.

A new network motifs visualization tool Mdraw is now available at:
http://www.weizmann.ac.il/mcb/UriAlon/ 


How to use mfinder ?
====================
Download the following files: mfinder.exe, network_exmp.txt, 
output_exmp.txt.

First check that the mfinder software runs properly on 
your computer, by the following step:

1. Open a DOS window
   (This can be done by : 
   		Start->Program->accessories->Command Prompt)

2. Change to the directory you downloaded the mfinder.exe 
   and the other two files.

3. Run the following command:

   mfinder.exe network_exmp.txt

4. Now you should see that the software start running
   (proper printing to the screen)

5. A successful run should end with the following line:
   "Output file network_exmp__OUT.txt was generated". 	
   
6. Check that you have an output file
   network_exmp_OUT.txt (in the same directory).
  

Once you managed to execute a simple mfinder run, you may want
to use the command line flags. If you don't use the command line
flag then the parameter is set to its default value as 
mentioned below. 

The general format is:

mfinder.exe <input network file name> [-s <motif size>] 
            [-r <num of random networks>] [-f <output file name>] 

Command line example:
=====================

mfinder.exe network_exmp.txt -s 4 -r 100 -f exmp_mtf_sz_4


Command line flags:
===================
-s :  Motif size to detect (currently can be 3 or 4).
	Default: 3
	
-r :  Number of random networks to generate.                
	Default: 100
	
-f :  Output file name. a suffix "__OUT.txt" is automatically 
      added.        
	Default: <input network file name>__OUT.txt
	
-nd : Input network is non-directed.
      (See input file format for this case)
	Default: Directed.

-omem : Output members of all the motifs that were found.
	
-h :  for help.
     
      (Or you can just type "mfinder.exe" for help).


Input file format
==================

Input network file format should be a simple ".txt" format.
Nodes in the network should be represented by integers.
Each edge in the network should be represented by an 
equivalent line of the following format:

<target node> <source node> <edge value>.

-In the current version <edge value> is ignored and should 
 be 1 for all edges.
-The number of nodes in the network is considered as the
 highest integer (that represent a node) to appear in the file.

Non-directed networks:
======================
If the network is non-directed, then every edge should appear
only once (means represented by only one line and not two).
The order of target and source has no meaning in this case.
(Pay attention: DO NOT represent a non-directed edge by the
two equivalent directed edges).
Remember to use the "-nd" flag when running mfinder with
non-directed networks.
  

You may look in the example file :network_exmp.txt
to see how your network input file should look like.


Enhanced command line flags:
============================
See mfinder tool guide.
        


Comments
========
1. If the number of random networks to generate is smaller 
   then 1000, then motifs criteria considers zscore>2 and 
   Pvalue is ignored (The number of random networks is not 
   large enough to consider Pvalue). 




Known Bugs/To be fixed 
======================

1.There are rare cases of overflows that causes probelms with hash 
  function when the mfinder is run with subgraph size >=6  
  (This bug still not fixed - TBD).
2. Subgraph ids for large nodes (6 and above) may be printed as negative numbers
   (this is ok, these numbers are larger than 32 bits and only the id is mal-printed).
  
  
Versions log:
=============
version 1.2
date: may 2005.
memebre file arranged.
small other fixes.

version 1.1:
date: aug 2003.
all memory leaks sorted.


  









