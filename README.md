# Dynamic Sequence Logos

This repo provides a script for analyzing and visualizing the Complementarity-Determining Regions (CDRs) from antibody structures in PDB format. The main script extracts CDR loops based on the Kabat numbering scheme, calculates their lengths, generates sequence logos for sequence conservation analysis, and provides an interactive widget for exploring the data.

## Features

-   **CDR Extraction**: Automatically identifies and extracts H1, H2, H3, L1, L2, and L3 loops from renumbered PDB files.
-   **Data Alignment**: Aligns sequences within each CDR type to enable direct comparison and generates a summary CSV file.
-   **Visualization**:
    -   Creates bar plots to show the distribution of CDR lengths.
    -   Generates sequence logos to visualize amino acid conservation at each position.
-   **Interactive Exploration**: A Jupyter Notebook widget allows for dynamic filtering of CDRs by type and length, and it generates sequence logos and pairwise identity matrices on the fly.

## Dependencies

To run this notebook, you will need Python 3 and the following libraries. You can install them using pip:

```bash
pip install pandas seaborn matplotlib logomaker biopython ipywidgets
```

-   **pandas**: For data manipulation and analysis, and for handling the CSV output.
-   **seaborn** & **matplotlib**: For generating plots of CDR length distributions.
-   **logomaker**: For creating sequence logos from aligned CDR sequences.
-   **biopython**: Used for parsing PDB files to extract structural information.
-   **ipywidgets**: Required for the interactive data explorer in the Jupyter environment.

## How to Use

1.  **Prepare PDB Files**: Place your Kabat-renumbered PDB files (with `.pdb` or `.ent` extensions) in a directory.
2.  **Run the Analysis Notebook** (`interactive_loops.ipynb`):
    -   Update the `PDB_DIRECTORY` variable to point to the location of your PDB files.
    -   Execute the cells in the notebook. The script will process the files and generate the output files listed below.
3.  **Explore Data Interactively**:
    -   Use the dropdown menu to select a specific CDR loop (`H1`, `L3`, etc.) or view all loops.
    -   Adjust the slider to filter the sequences by their biological length.
    -   The table, sequence logo, and pairwise identity matrix will update automatically based on your selections.

## Output Files

The analysis script will generate the following files in the same directory:

-   `cdr_summary_aligned.csv`: A CSV file containing the extracted CDRs, their lengths, and the aligned sequences.
-   `cdr_length_distribution.png`: A plot showing the frequency of different CDR lengths.
-   `<CDR_NAME>_sequence_logo.png`: Sequence logos for each CDR type (e.g., `H1_sequence_logo.png`, `H3_sequence_logo.png`).
