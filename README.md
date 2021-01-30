# PROCON-dataset

## Research problem description
An important issue faced during software development is to identify defects and the properties of those defects, if found, in a given source file. Determining defectiveness of source code assumes significance due to its implications on software development and maintenance cost. 

## Motivation behind developing PROCON metrics or PROCON dataset
Developing source code involves making programming decisions that affect the software quality [1-4]. The programming decisions made while constructing the software influence its quality attributes such as readability, portability, ease-of-learning, reliability and maintainability [3]. For instance, the choice of concise and consistent naming conventions (for identifier names) has been reported [4-5] to result in better quality software. The above results indicate the existence of a relationship between the programming decisions employed in constructing a software and the quality of the software.  We develop a Defect Estimator for Source Code (DESCo) [2] for determining the defectiveness of source code by analyzing the programming decisions employed in constructing it. This intuition of determining the defectiveness of source code by analyzing the constituent programming decisions forms the motivation of PROgramming CONstruct (PROCON) metrics.

### How do we define a programming decision?
A programming decision includes the following type of syntactic decisions made by the programmer during construction of a program:

1. Choice of the programming language constructs. For example, *for* vs. *do-while* for looping, *if-else* vs. *switch* for branching.
2. The constructs' occurrence **count** and **depth** in the **parse tree** of the source code. For example, the *if* statement is used *100 times* in a source file with the deepest nesting level of, say, *5*.
3. The **length** of the names of various elements of the program. For example, the names of variables, functions, and classes.

Following are not considered the programming decisions:
1. The **exact names** of the **variables, functions** and **classes**. We only care about the length of names, not the names itself.
2. **Abstract design choices** such as those made during architecture design. For instance, whether to use *factory method* vs. *abstract factory design pattern*.


## What are PROCON metrics?
PROgramming CONstructs (PROCON) metrics dataset was developed to capture a representation of programming constructs usage patterns in a given source code. For a programming construct **X** present in a source code file, PROCON metrics imply the **max, min, avg,** and **stdDev** of the **count, depth,** and **length** of **X** at **function, class,** and **file** level. The complete detail of the programming constructs considered is shown in the table below:

![PROCONconstructs](https://user-images.githubusercontent.com/76653789/106340646-c389b680-629a-11eb-8d97-3fdfa6501a7b.png)

## What does the PROCON dataset comprise?
To develop the PROCON dataset, we extracted PROCON metrics' values by processing 30400+ source files from 20+ GitHub repositories. The source files were written in four popular programming languages, viz. C, C++, Java, and Python. We used ANTLR tool to parse the source code, and develop a feature extractor module to extract the PROCON metrics values. As the programming constructs differ among various programming languages, we developed language-specific PROCON datasets. The complete details of source files in language-specific PROCON datasets is as follows:

![sourceFiles](https://user-images.githubusercontent.com/76653789/106340959-ca64f900-629b-11eb-8ad8-d5814b4af5ac.png)
 
## How does DESCo perform?
DESCo system when trained on PROCON datasets outperforms one of the state-of-the-art methods with an improvement of 44.9%. When compared with the PROMISE repository's CK's metrics dataset, DESCo-PROCON combination achieves an improvement of 29.9%. We validated the correctness of our system, by compared the performance of 12 different ML algorithms with 50+ different combinations of their key parameters. Our system achieves the best results with SVM technique with a mean accuracy measure of 80.8%. DESCo paper is available at https://dl.acm.org/doi/abs/10.1145/3384517.

## Relational Schema of PROCON

![PROCON-design](https://user-images.githubusercontent.com/76653789/106337775-612cb800-6292-11eb-9e2b-831367de29b3.png)

## Installation instructions

1. If not already available, install **MySQL 5.7** or higher on your machine. 
2. Ensure that you have at least 10GB of disk space available. 
3. Download the **PROCON.sql** file from the this github repository. You can also clone the entire repository and then unzip the contents. 
5. Import the data into your MySQL server using this command: **mysql -u #your_username# -p #database_name# > #path_to_PROCON.sql_file#** and then enter your password.

**Note:** *Replace #your_username# with your mysql username and  #database_name# with the mysql database name when the data is to be imported.*

### References

1. Ritu Kapur and Balwinder  Sodhi. “Towards  a  knowledge  warehouse  and  expert system for the automation of sdlc tasks.” 2019 IEEE/ACM International Conference on Software and System Processes (ICSSP). IEEE,  2019, pp. 5–8.
2. Ritu Kapur and Balwinder Sodhi. "A defect estimator for source code: Linking defect reports with programming constructs usage metrics." ACM Transactions on Software Engineering and Methodology (TOSEM) 29.2 (2020): 1-35.
3. M. Allamanis, E. T. Barr, C. Bird, and C. Sutton. “Learning natural codingconventions.”  22nd ACM SIGSOFT International Symposium on Foundations of Software Engineering. ACM,  2014, pp. 281–293.
4. F. Deissenboeck and M. Pizka. “Concise and consistent naming.” Software Quality Journal, vol. 14, no. 3, pp. 261–282, 2006.
5. D. Lawrie, C. Morrell,  H. Feild, and D. Binkley. “What’s  in a name? a study of identifiers.” 14th IEEE International Conference on Program Comprehension. IEEE, 2006, pp. 3–12.

### Contributors 
Ritu Kapur and Balwinder Sodhi, Indian Institute of Technology, Ropar, India.

### Code of Conduct
Please note that this project is released with a **Contributor Code of Conduct.** By participating in this project you agree to abide by its terms.

## Copyright
GNU Affero License &copy; 2018 Ritu Kapur and Balwinder Sodhi.
