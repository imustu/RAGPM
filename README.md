# RAGPM and GSS

# 🧬 Ancestral Genome Reconstruction & Simulation Programs

**Programs Included: RAGPM (Reconstruction) and GSS (Simulation)**

| Feature | Details |
| :--- | :--- |
| **Current Version** | 1.0 |
| **Programming Language** | Java |
| **Required Java Version** | **Java 14 or higher** |

-----

## 1\. RAGPM: Ancestral Genome Reconstruction

### 1.1 What is RAGPM?

RAGPM (Reconstructing Ancestral Gene Orders as Contiguous Ancestral Regions) is a program designed to reconstruct Ancestral gene orders. It utilizes a method based on probability and adjacency pairs. The program outputs the reconstructed genome as CARs (Contiguous Ancestral Regions).

### 1.2 Input Requirements

The method requires two primary input files and a designated output directory:

1.  **Phylogenetic Tree File:** The tree structure must be formatted in **Newick format**. (Example: `example_for_RAGPM/newick_Tree`) .
2.  **Leaf Genomes File:** A file containing the genomes of all **leaf nodes** on the phylogenetic tree. (Example: `example_for_RAGPM/leafGenomes_for_RAGPM`) .
3.  **Output Directory:** The directory where results will be saved.

### 1.3 Output Files

The results will be placed in the specified output directory:

  * **`process`:** A file holding the brief process of reconstructing all ancestral (branch) nodes.
  * **`RAGPM_Reconstructed_nodeNum`:** For each ancestral node, a separate file holding the reconstructed genome of that node.

### 1.4 Command Usage

To execute RAGPM, use the following command structure:

```bash
java -jar RAGPM.jar [PathOfTree] [PathOfLeafGenomes] [outDirectory]
```

**Example:**

```bash
cd examples/example_for_RAGPM/
java -jar RAGPM.jar newick_Tree leafGenomes_for_RAGPM ./
```

> *Note: If input files are not in the same directory, please specify their absolute paths.*

-----

## 2\. GSS: Genome Simulation System

### 2.1 What is GSS?

GSS (Genome Simulation System) is a program used to generate examples of **simulated evolutionary processes**. Its design thinking is detailed in `ideas_GSS.docx`.

### 2.2 Input Requirements

1.  **Phylogenetic Tree File:** The tree structure must be formatted in **Newick format**. (Example: `example_for_GSS/tree.txt`) .
2.  **Root Genome File:** A file holding the genome of the **root-node**. (Example: `example_for_GSS/rootGenome.txt`) .
3.  **Parameters File:** A file to specify the evolutionary parameters involved. (Example: `example_for_GSS/parameters.txt`) .
      * **Line 1:** The total sum of events occurring on all branches on the tree.
      * **Line 2:** The proportion of the four types of events occurring (reversal, transposition, translocation, fission-and-fusion).

### 2.3 Output Files

For each node in the tree, two files will be generated in the output directory:

1.  **`nodeName_chromosomes.txt`:** Holds the genome of the node.
2.  **`nodeName_options.txt`:** Holds the process of generating the node.

### 2.4 Command Usage

To execute GSS, use the following command structure:

```bash
java -jar GSS.jar [PathOfTree] [PathOfParameters] [PathOfRootGenome] [outPath]
```

**Example:**

```bash
cd examples/example_for_GSS/
java -jar GSS.jar tree.txt rootGenome.txt parameters.txt ./
```

> *Note: If input files are not in the same directory, please specify their absolute paths.*

-----

## 3\. Supplementary Information

### 3.1 Source Code Availability

The source code for the programs is shared respectively at:

  * **RAGPM:** `RAGPM_source`.
  * **GSS:** `GSS_source`.

### 3.2 Shared Data

  * **Simulation Samples:** `data/All.zip`.
  * **Real Sample:** `data/realSample.zip`.

### 3.3 Contact

**Please send bug reports and technical questions to Yuan Zhang at zhangyuan@mail.imu.edu.cn.
