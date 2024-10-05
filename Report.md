# **Authors**

Logy Khaled (@Logy), Alaa Hewela (@Alaa253), Tawfek Ahmed Tawfek (@Tawfekahmed25), Rahma mamdouh Mohammed (@Rahmamam2000), Malak Abdelfattah Soula (@Malak), Zeyad Ashraf (@Zashraf03), Nourhan Mahmoud (@NourhanM1) , Mohammed Dahab (@mdahab7)

# **GithubRepository**

[Repository_Stage_4_task](https://github.com/Logykh/Stage-4/tree/main)

[R source code](https://github.com/Logykh/Stage-4/blob/main/Code%20.R)

[Python source code](https://github.com/Logykh/Stage-4/blob/main/HackBio_stage_4_ML.py)
# **Introduction**

Gliomas are brain tumors with significant heterogeneity, where mutations in the IDH (Isocitrate Dehydrogenase) gene serve as key biomarkers for prognosis and treatment. IDH mutant and wildtype statuses classify gliomas and predict patient outcomes. The study of gene expression data enhances the understanding of molecular differences.

# **Dataset and Preprocessing**

We used gene expression data from the TCGA-LGG cohort, downloaded via TCGABiolinks, and matched with IDH status. Preprocessing involved removing samples with missing IDH status and filtering genes with over 25 zero values. Data normalization ensured consistency for analysis.

# **Results**

Differential expression analysis was conducted using DESeq2 to identify differentially expressed genes between IDH wildtype and mutant gliomas based on an adjusted p-value \< 0.05 and |log2FoldChange| \> 1\. 

The MA plot visualizes the log fold change versus mean normalized counts. Significant outliers indicate potential biomarkers.

![IMG-20241004-WA0030](https://github.com/user-attachments/assets/de7240a3-3a24-455d-9364-32807203641b)

# **Comparison with Target Paper**

Our findings supported the original study’s clustering based on IDH status. However, updated gene expression data suggests that additional clusters may be necessary to uncover more molecular subtypes beyond the six clusters.

# **Machine Learning Approach for Gene Expression Clustering Using K-Means**
We performed K-Means clustering on a gene expression dataset **as the same data used in the paper** using the `K-Means` algorithm after applying dimensionality reduction with **`Principal Component Analysis (PCA)`**.

The gene expression data was normalized with StandardScaler for consistent feature scaling. PCA was then applied to reduce dimensionality to two components, retaining most of the variance. These two components enabled effective visualization of the clusters.


Using K-Means with six clusters, we identified distinct clusters. The clustering performance was evaluated using the `Silhouette Score`, a measure of how similar samples in the same cluster are compared to those in other clusters. We achieved an impressive Silhouette Score of 93.29%, indicating that the clusters were well-formed and separated.

### **K-mean clustering gene expression data with PCA**
The PCA plot showed distinct groupings along with some outliers, which may indicate biological variations or technical noise. This unsupervised clustering method offers insights into gene expression patterns and holds potential implications.

![K-mean clustering gene exp (PCA)](https://github.com/user-attachments/assets/25e4591f-d7b4-4992-8c88-214006d9c23a)


# **Conclusion**

The analysis confirms IDH status is crucial in glioma classification using gene expression data. It suggests new glioma subtypes, encouraging further research into biomarkers and refined treatment strategies.

**Increasing clusters reveals distinct glioma subgroups, improving understanding of heterogeneity. Integrating newer multi-omics datasets, like copy number variation, may identify more clusters for precise molecular stratification.**
