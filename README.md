# gmx_cyclizer.py
Script for 
1. trimming and reordering atom indices in cyclic.top file
2. reordering atom indices in porse_cyclic.itp file
3. merging the receptor's .gro file and cyclic peptide's .gro file into one

input parameters:

			command line parameters:
			1     name of cyclic.top file
			2     name of cyclic.gro file
			3 (opt) receptor's .gro file

output file:

			1		 	topol_cyclic.itp file
			2		  posre_cyclic.itp file
			3	  	cyclic.gro or complex.gro file
