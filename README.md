Full workflow for generating graphs from a selection of database files, using those graphs to train an encoder, generating structural fingerprints and analysing them using hsdbscan and
dimensionality reduction algorithms.

The workflow is split into 5 files as follows:
1) Sublattice generation - takes database files and strips each structure into its constituent sublattices which are then saved as individual structure.xyz files.
2) Supercell generation - takes the sublattice structures generated in 1 (or any other folder of single unit cell structure files) and converts them into a folder of supercells.
3) Graph generation - takes the supercells generated in 2 (note two folders of differnent supercell sizes will be needed here) and turns them into graphs. Applies perturbations
and saves them along with one set of unperturbed graphs.
4) Model and fingerprints workflow - takes the graphs and uses them to train a GNN encoder. Once trained (the user can stop this at any time), the final embeddings can be made
and saved.
5) Clustering - takes the final embeddings and clusters them. The clusters are visualised using dimensionality reduction algorithms (t-SNE or UMAP) and can be analysed using a
variety of code found within the file.

Note: the materials folder only comes with a single file 'reduced_sublattice_structure.txt'. If using this dataset, you can simply skip 1) and go straight to 2) using the
flatband dataset code cell. The model works best on the entire '2DMatpedia.json' file but this needs to be downloaded separately and placed in the 'Materials' folder.
The workflow can also be ran using the 'c2db.db' file but that also needs to be downloaded separately.
Several python libraries will need to be installed for the code to work.
