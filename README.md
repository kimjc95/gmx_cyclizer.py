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

			1	topol_cyclic.itp file
			2	posre_cyclic.itp file
			3	cyclic.gro or complex.gro file

Before GROMACS ver. 2021 update, it was difficult to generate the cyclic peptide's topology with pdb2gmx.
This script automates the process.

## How to use
### 1. Prepare the linearized peptide's topology
pass down your cyclic peptide's .pdb file into pdb2gmx with -ter option. Select no modification on the termini.

	gmx pdb2gmx -f input_peptide.pdb -o linear_peptide.gro -ter

### 2. Manually edit the linearized peptide's .gro file
Open the .gro file generated from the previous step with text editor.
Copy the last residue's atom coordinates and paste before the first residue.
Copy the first residue's atom coordinates and paste after the last residue.

### 3. Use gmx_cyclizer.py!
Feed the topology file and the edited coordinate file into the gmx_cyclizer.py.
If present, feed the receptor's atom coordinates with an additional .gro file.

	python gmx_cyclizer.py peptide.top peptide.gro

or

	python gmx_cyclizer.py peptide.top peptide.gro receptor.gro

### 4. Enjoy simulation!
