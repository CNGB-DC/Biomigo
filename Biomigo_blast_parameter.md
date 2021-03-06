## v-1.0 基本参数：
*   Expect threshold (E threshold)（evalue &lt;Real&gt;）：Expectation value (E) threshold for saving hits Default = `**<font color="#ff0000">10</font>**'.
*   Alignment view（outfmt &lt;String&gt;）：

   *   0 = Pairwise,
   *   5 = BLAST XML,
   *   6 = Tabular,

*   Alignments（num_alignments &lt;Integer &gt;）：Number of database sequences to show alignments for Default = `250'，* Incompatible with:  max_target_seqs

   *   250
   *   500
   *   1000
   *   2000
   *   20000

----

## v-1.1 新增参数 (参考)：

*  **-word_size**：word_size &lt;Integer&gt;,Word size for wordfinder algorithm (length of best perfect match).

   设定字长大小，blastn为11， megablast 为28，其他为3。

   1. **[ncbi blast](https://blast.ncbi.nlm.nih.gov/Blast.cgi?PROGRAM=blastn&PAGE_TYPE=BlastSearch&LINK_LOC=blasthome)：**( **粗体** 为网站默认值)
      *   blastn：7、**11**、15, &lt;Integer, &ge;4&gt;
      *   blastp：2、3、**6**
      *   blastx：2、3、**6**
      *   tblastn：2、3、**6**
      *   tblastx：2、**3**

   2. **biomingo_blast values：**
      *   **blastn：from 4 to 15, sep=1**
      *   **others：from 2 to 15, sep=1**

*  **-gapopen**：Cost to open a gap \[Integer\]

   起始空位罚分。
   
*  **-gapextend**：Cost to extend a gap.

   空位延伸罚分。

   1. **[ncbi blast](https://blast.ncbi.nlm.nih.gov/Blast.cgi?PROGRAM=blastn&PAGE_TYPE=BlastSearch&LINK_LOC=blasthome)：**

      *   **blastn：**(gapopen, gapextend) = (**5, 2**)
   
      ![blastn](https://github.com/CNGB-DC/Biomigo/blob/master/Images/blastn_gap_parameter.png)
   
      *   **blastp、blastx、tblastn：**(gapopen, gapextend) = (**11, 1**)
   
      ![blastp](https://github.com/CNGB-DC/Biomigo/blob/master/Images/blastp-x_gap_parameter.png)
   
      *   **tblastx：**无
   
   2. **biomingo_blast values：**（以 [NBK279675](https://www.ncbi.nlm.nih.gov/books/NBK279675/) 为标准）
   
      *   **blastn：**
          
          * gapopen:6 gapextend:2
          * gapopen:5 gapextend:2
          * gapopen:4 gapextend:4
          * gapopen:3 gapextend:3
          * gapopen:2 gapextend:4
          * gapopen:2 gapextend:2
          * gapopen:0 gapextend:4
          
      *   **others(except tblastx)：**
          
          * gapopen:13 gapextend:1
          * gapopen:12 gapextend:1
          * gapopen:11 gapextend:2
          * gapopen:11 gapextend:1
          * gapopen:10 gapextend:2
          * gapopen:10 gapextend:1
          * gapopen:9 gapextend:2
          * gapopen:9 gapextend:1
          * gapopen:8 gapextend:2
          * gapopen:7 gapextend:2
          * gapopen:6 gapextend:2

*  **-matrix**：Comparison Matrix（default = BLOSUM62）

   1. **[ebi blast](http://www.ebi.ac.uk/Tools/sss/ncbiblast/nucleotide.html)：**

      *   blastn：无
   
      *   blastp、blastx、tblastn、tblastx：BLOSUM45、BLOSUM50、BLOSUM62（default）、BLOSUM80、BLOSUM90、PAM30、PAM70、PAM250

   2. **biomingo_blast values(except blastn )：**

      *   **BLOSUM45、BLOSUM50、BLOSUM62（default）、BLOSUM80、BLOSUM90、PAM30、PAM70、PAM250**

