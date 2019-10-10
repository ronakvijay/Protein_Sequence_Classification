# Protein_Sequence_Classification
A case study on Pfam dataset to classify protein families.

__Blog Post: https://towardsdatascience.com/protein-sequence-classification-99c80d0ad2df__

### Description
Proteins are large, complex biomolecules that play many critical roles in biological bodies. Proteins are made up of one or more long chains of amino acids sequences. These Sequence are the arrangement of amino acids in a protein held together by peptide bonds. Proteins can be made from 20 different kinds of amino acids, and the structure and function of each protein are determined by the kinds of amino acids used to make it and how they are arranged.

Understanding this relationship between amino acid sequence and protein function is a long-standing problem in moleculer biology with far-reaching scientific implications. Can we use deep learning that learns the relationship between unaligned amino acid sequences and their functional annotations across all 17929 families of the <a href='https://en.m.wikipedia.org/wiki/Pfam'>Pfam</a> database.

Pfam is a database of protein families that includes their annotations and multiple sequence alignments.

### Problem Statement
- Classification of protein's amino acid sequence to one of the protein family accession, based on PFam dataset.
- In other words, the task is: given the amino acid sequence of the protein domain, predict which class it belongs to.

### Deep learning Models
I have referred <a href='https://www.biorxiv.org/content/10.1101/626507v4.full'>this</a> paper for defining model architectures and trained two separate models, one is bidirectional LSTM and the other one is inspired from ResNet a CNN based architecture.

#### ProtCNN
This model uses residual blocks inspired from ResNet architecture which also includes dilated convolutions offering larger receptive field without increasing number of model parameters.

<br/>
<center><img src='https://www.biorxiv.org/content/biorxiv/early/2019/07/15/626507/F6.large.jpg' height='470' width='700'></center>
<br/>

### Conclusion
The ProtCNN model has achieved significant results which are more accurate and computationally efficient than current state of the art techniques like <a href='https://en.wikipedia.org/wiki/BLAST_(biotechnology)'>BLASTp</a> to annotate protein sequences. These results suggest deep learning models will be a core component of future protein function prediction tools.

<table>
  <tr>
    <th>Model</th>
    <th>Train Acc</th>
    <th>Val Acc</th>
    <th>Test Acc</th>
  </tr>
  <tr>
    <th>Bidirectional LSTM</th>
    <th>0.964</th>
    <th>0.957</th>
    <th>0.958</th>
  </tr>
  <tr>
    <th>ProtCNN</th>
    <th>0.996</th>
    <th>0.988</th>
    <th>0.988</th>
  </tr>
</table>

#### Reference: https://www.biorxiv.org/content/10.1101/626507v4.full
