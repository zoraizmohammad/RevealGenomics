Important Instructions About Data: There's a file in the folder called
DataExploration.ipynb The gene expression data is located in the
RevealGenomics project folder and is called TCGA_PanCancer_data.tsv The
metadata is also located in the project folder and is called
merged_sample_quality_annotations.tsv. The metadata includes information
about each cell such as what type of cancer cell it is Run all of the
code in DataExploration.ipynb. Here is what I have done in it: Any genes
with NaN values have been removed from the gene expression The metadata
has been filtered to only include cells that are in the gene expression
data The gene expression data and the metadata have been merged together
The final gene expressions have been log-normalized I have placed the
final dataset in an AnnData object called adata_tcga at the end of the
DataExploration file You can access the gene expression counts by
running adata_tcga.X You can access information about the cells by
running adata_tcga.obs, including what type of cancer cell it is Each
row in the dataset represents a cell and each column is a gene.
Therefore, each row is all of the gene expression counts for a single
cell. The gene expression data in adata_tcga.X should be the starting
point for the autoencoders. You can convert it into a pandas dataframe
if that makes it easier to work with. Your goal with the autocounters is
to create a lower-dimensional representation of the gene expression
counts for every cell. In the final dataset, each cell has 16335 genes,
so it can be represented by a 16335-dimensional vector. You want to use
an autoencoder to reduce the representation

Tasks for this Week: Read the above instructions about the data
Understand Figure 2 in the following paper and read at least the
abstract: https://pubmed.ncbi.nlm.nih.gov/29218871/ It would also be
helpful to read the introduction to get more context on the paper Get
familiar with autoencoders, how to use them, and understand their
purpose Tensorflow autoencoder documentation:
https://www.tensorflow.org/tutorials/generative/autoencoder Start to
investigate how an autoencoder can be applied to the TCGA dataset and
how it can create low-dimensional representations of the data

Initial Steps: First we want to try to replicate Figure 2 from the paper
above using autoencoders to create a low-dimensional representation of
the data We want to cluster each cell by cancer type and see if we can
get clusters similar to those shown below Each dot represents a cell and
every color is a certain cancer type We will use an autoencoder to
create a low-dimensional representation of each cell and will plot those
low-dimensional representations in a manner similar to the figure below
to see if the cancer cell types cluster together

We will first be working with the TCGA (Cancer Genome Atlas) dataset:
https://www.genome.gov/Funded-Programs-Projects/Cancer-Genome-Atlas
