# LungOncoML- Sammy
LungOncoML is a machine learning project designed to classify lung tissue samples as cancerous or normal using RNA-Seq gene expression data. The main idea of this project is to combine bioinformatics and machine learning techniques to understand complex biological data and make accurate predictions about lung cancer. The project uses real publicly available data from the GEO database (GSE19804), which contains thousands of genes measured across multiple lung tissue samples.

The first step in the project is loading and organizing the data. Each row in the dataset represents a tissue sample, and each column represents a gene. To make the dataset usable for machine learning, I created labels for each sample: 1 for cancerous and 0 for normal tissue. This labeling was done automatically by checking the metadata for each sample, which ensures that the classification is accurate and consistent.

RNA-Seq datasets have tens of thousands of genes, which can make training models very slow and noisy. To handle this, I implemented a gene reduction step. I calculated the variance of each gene across all samples and selected the top 500 genes with the highest variance. This focuses on genes that show the most difference between normal and cancer tissue, which makes the models more accurate and the analysis more meaningful.

After selecting the most important genes, I standardized the data so that all gene expression values are on the same scale. This step is crucial because machine learning algorithms, like Logistic Regression and Random Forest, perform better when features are scaled properly.

For visualization, I applied Principal Component Analysis (PCA). PCA reduces the data to two dimensions so it can be plotted easily. The PCA plot shows clear separation between normal and cancer samples, which is satisfying to see and gives confidence that the data contains meaningful patterns. This visual insight is an important step in bioinformatics analysis, as it helps to understand the structure of the data before training models.

Next, I trained two machine learning models: Logistic Regression and Random Forest. The data was split into 80% for training and 20% for testing. The models learn patterns in the gene expression data that distinguish cancerous tissue from normal tissue. Logistic Regression is simple and interpretable, while Random Forest can capture more complex patterns. Both models were evaluated on the test data, and their accuracy was calculated. The Random Forest model performed exceptionally well, demonstrating its ability to handle high-dimensional biological data.

One of the most exciting aspects of this project is that the models can predict new samples. When a new lung tissue sample is measured, the same 500 genes are selected, scaled, and fed into the model. The model then predicts whether the sample is cancerous or normal. This workflow shows the practical application of machine learning in bioinformatics and healthcare analytics.

Overall, LungOncoML demonstrates the full pipeline of a bioinformatics machine learning project: from raw RNA-Seq data handling, gene selection, and scaling, to visualization, model training, evaluation, and prediction. This project helped me understand how to work with high-dimensional data, reduce complexity, and build predictive models. It is a strong example of how computational biology and machine learning can be combined to tackle real-world problems, making it a great project to showcase for internships in bioinformatics, computational biology, or healthcare analytics.

## Features

- RNA-Seq gene expression data handling  
- Top 500 gene selection for dimensionality reduction  
- PCA visualization of data  
- Logistic Regression & Random Forest models  
- Prediction for new samples  
- Accuracy evaluation on test data  


