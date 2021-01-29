# PROCON-dataset

**Brief Information:** PROgramming CONstructs (PROCON) metrics dataset was developed to capture the programming 
 
**Abstract:** An important issue faced during software development is to identify defects and the properties of those defects, if found, in a given source file. Determining defectiveness of source code assumes significance due to its implications on software development and
maintenance cost. 

Programming decisions made by a constructing the software affect the software quality.  We develop a Defect Estimator for Source Code (DESCo) for determining the defectiveness of source code by analyzing the programming decisions employed in constructing it. This intuition of determining the defectiveness of source code by analyzing the constituent programming decisions forms the motivation of PROgramming CONstruct (PROCON) metrics.
The language-specific PROCON datasets were created by processing 30400+ source files from 20+ GitHub repositories. The source files were written in four popular programming languages, viz. C, C++, Java, and Python.

DESCo system when trained on PROCON datasets outperforms one of the state-of-the-art methods with an improvement of 44.9%. When compared with the PROMISE repository's CK's metrics dataset, DESCo-PROCON combination achieves an improvement of 29.9%. We validated the correctness of our system, by compared the performance of 12 different ML algorithms with 50+ different combinations of their key parameters. Our system achieves the best results with SVM technique with a mean accuracy measure of 80.8%. DESCo paper is available at https://dl.acm.org/doi/abs/10.1145/3384517.

![alt text](https://github.com/RituKapur-Developer/PROCON-dataset/blob/main/DEfectEstimation_design.pdf)


