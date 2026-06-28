 # Data Pipeline Part 2 - MCQ Exam

Time allowed: 60 minutes  
Number of questions: 48  
Scoring: 1 point per question, no negative marking  
Instruction: Choose exactly one correct answer for each question.

## Questions

1. What is the main engineering goal of the Data Pipeline Part 2 course?
   A. To train and tune deep learning models only  
   B. To build and deploy batch ETL pipelines using modern data engineering practices  
   C. To design manual dashboards without automation  
   D. To replace software engineering practices with notebook-only workflows  

2. Which sequence best represents the data product lifecycle discussed in class?
   A. Deployment, monitoring, ideation, deletion  
   B. Ideation and experimentation, development, industrialization, monitoring  
   C. Collection, backup, visualization, archiving  
   D. Modeling, coding, billing, reporting  

3. Why are agreed interfaces important in production data systems?
   A. They allow components to communicate reliably without depending on internal implementation details  
   B. They remove the need for schema design  
   C. They guarantee that no tests are needed  
   D. They force every component to use the same programming language  

4. What is data modelling mainly concerned with?
   A. Designing structured representations of data for efficient storage, management, and analysis  
   B. Choosing the color scheme of a dashboard  
   C. Compressing every file into a single binary object  
   D. Running SQL queries without considering consumers  

5. Which pair correctly matches data modelling stages to their purpose?
   A. Conceptual: business entities; logical: relationships and structure; physical: storage implementation  
   B. Conceptual: CPU sizing; logical: cloud billing; physical: UI design  
   C. Conceptual: unit tests; logical: Git branches; physical: Docker images  
   D. Conceptual: encryption keys; logical: monitoring alerts; physical: sprint planning  

6. Which statement best distinguishes OLTP from OLAP?
   A. OLTP supports real-time transactional workloads, while OLAP supports analytical queries and decision-making  
   B. OLTP is only for data lakes, while OLAP is only for mobile apps  
   C. OLTP never requires data integrity, while OLAP never uses SQL  
   D. OLTP is slower because it always stores more historical aggregates than OLAP  

7. In a star schema, what is the typical relationship between tables?
   A. One central fact table connects directly to dimension tables  
   B. All dimension tables are fully nested inside JSON arrays  
   C. Every table must have exactly one row  
   D. There are no keys between facts and dimensions  

8. What is a snowflake schema?
   A. A model where dimension tables are further normalized into related sub-tables  
   B. A model that stores every metric in one unstructured text column  
   C. A model used only for streaming logs  
   D. A model that avoids primary keys by design  

9. What does First Normal Form (1NF) require?
   A. Values in each column should be atomic, with no repeating groups in a single cell  
   B. Every table must contain only one column  
   C. All tables must be denormalized for faster reads  
   D. Foreign keys must be removed from the design  

10. What does Second Normal Form (2NF) remove?
    A. Partial dependencies on part of a composite primary key  
    B. All indexes from a database  
    C. Every relationship between tables  
    D. All historical data from dimension tables  

11. What does Third Normal Form (3NF) remove?
    A. Transitive dependencies where non-key attributes depend on other non-key attributes  
    B. Primary keys from fact tables  
    C. Atomic values from columns  
    D. All joins from analytical queries  

12. When is normalization usually most useful?
    A. When reducing redundancy and avoiding insertion, update, and deletion anomalies is important  
    B. When the only goal is to maximize duplicate storage  
    C. When every analytical query must avoid joins  
    D. When schemas are not needed  

13. What is a Slowly Changing Dimension (SCD)?
    A. A dimension attribute that changes over time and must be handled in the model  
    B. A fact table that can never be updated  
    C. A streaming topic with no schema  
    D. A table that is deleted after every batch run  

14. In dimensional modelling, what is usually stored in a fact table?
    A. Measurable events or metrics, often linked to dimensions through keys  
    B. Only application source code  
    C. Only user interface settings  
    D. Only normalized lookup labels with no metrics  

15. Why can bucketing improve joins in large analytical tables?
    A. It can colocate rows with the same join key, reducing expensive data shuffles  
    B. It converts every join into a cross join  
    C. It removes the need for partitioning or sorting in every case  
    D. It stores all rows on a single worker  

16. What does a DatelistInt representation enable?
    A. Encoding multiple days of activity into an integer so efficient bitwise operations can be used  
    B. Replacing all dimension tables with Python lists  
    C. Running joins without any keys  
    D. Storing images inside a relational primary key  

17. The "Justin Bieber problem" in data engineering is best understood as what?
    A. Data skew or hot keys where a small part of the data receives disproportionate traffic  
    B. A problem caused only by missing Python type hints  
    C. A limitation that appears only in single-row tables  
    D. A failure caused by using cloud storage instead of local files  

18. In data engineering, what does it mean for an operation to be idempotent?
    A. Running it multiple times on the same input produces the same final target state without duplicate effects  
    B. It always runs faster on the second attempt  
    C. It must never write to a database  
    D. It only works for streaming data  

19. Why are stateless functions often preferred in data pipelines?
    A. They are easier to reason about, test, and compose because they do not depend on hidden internal state  
    B. They automatically create larger clusters  
    C. They prevent any need for schemas  
    D. They force all jobs to run sequentially  

20. When is a factory pattern useful in ETL code?
    A. When multiple pipelines follow a similar structure but need different concrete implementations  
    B. When all business logic should be hard-coded into one function  
    C. When tests should be skipped for faster delivery  
    D. When data should be stored only in nested dictionaries  

21. What is the main idea of the strategy pattern?
    A. Encapsulate interchangeable algorithms or behaviors behind a common interface  
    B. Store secrets in source code to simplify deployments  
    C. Replace all classes with global variables  
    D. Execute all transformations immediately  

22. What does a Python context manager help with?
    A. Acquiring and releasing resources such as files or database connections reliably  
    B. Increasing the number of Spark executors automatically  
    C. Creating GitLab runners  
    D. Rewriting Iceberg manifests  

23. Why are dataclasses often preferable to deeply nested dictionaries for complex objects?
    A. They make structure and types explicit, improving readability and maintainability  
    B. They prevent any object from being serialized  
    C. They remove the need for constructors in every language  
    D. They make all fields mutable global constants  

24. What is dependency injection?
    A. Passing dependencies such as data sources or connections into a component instead of hard-coding them  
    B. Installing dependencies during every CI job without caching  
    C. Injecting duplicate rows into a target table  
    D. Creating a new database for every function call  

25. What is premature optimization?
    A. Improving performance before the real bottlenecks or requirements are understood  
    B. Testing code before deployment  
    C. Removing duplicated constants from source code  
    D. Choosing an open table format for a lakehouse  

26. Which statement best describes Hadoop MapReduce?
    A. A distributed processing model that divides work into map and reduce phases  
    B. A Git workflow for reviewing merge requests  
    C. A Terraform command for provisioning infrastructure  
    D. A table format for schema evolution  

27. Why did Spark improve many workloads compared with classic Hadoop MapReduce?
    A. Spark can use in-memory computation and a richer execution model for iterative and analytical workloads  
    B. Spark writes every intermediate result to disk by design  
    C. Spark only runs on one machine  
    D. Spark removes the need for distributed storage  

28. What is an RDD in Spark?
    A. An immutable distributed collection that can be processed in parallel  
    B. A GitLab pipeline variable  
    C. A Terraform provider  
    D. A Parquet footer only  

29. What does Spark lazy evaluation mean?
    A. Transformations are recorded in a logical plan and executed only when an action requires results  
    B. Spark deliberately waits a fixed number of seconds before every task  
    C. DataFrames cannot be optimized  
    D. Executors never run code until the driver is restarted  

30. Which operation is usually a narrow transformation?
    A. A filter where each child partition depends on at most one parent partition  
    B. A groupBy that redistributes rows by key across the cluster  
    C. A join that shuffles both large tables by key  
    D. A global sort across all partitions  

31. What makes wide transformations expensive in Spark?
    A. They often require a shuffle across the network  
    B. They only use CPU caches and no network  
    C. They are always executed on the driver only  
    D. They never materialize intermediate data  

32. What happens in a broadcast join?
    A. A small dataset is sent to executors so it can be joined locally with a larger dataset  
    B. Both large datasets are always sorted on disk before joining  
    C. The driver collects both datasets and joins them in local memory  
    D. Spark disables partitioning for the join key  

33. When is a shuffle hash join typically relevant?
    A. When datasets need to be repartitioned by join key and a hash table is built from the smaller side  
    B. When one side is small enough to broadcast to all executors  
    C. When the result should be written only as JSON  
    D. When there is no join condition  

34. What is the core idea of a sort-merge join?
    A. Shuffle by key, sort both sides within partitions, then merge matching keys  
    B. Broadcast the larger table to the smaller table  
    C. Convert all numeric keys to strings before joining  
    D. Disable sorting so joins can avoid comparisons  

35. Why is using collect() carelessly risky in Spark?
    A. It brings distributed data back to the driver and can exhaust driver memory  
    B. It always improves cluster parallelism  
    C. It permanently deletes executor logs  
    D. It changes an Iceberg table schema  

36. What is a good testing practice for PySpark applications?
    A. Structure code so transformations can be tested with a reusable SparkSession and injected dependencies  
    B. Test only by manually inspecting production tables  
    C. Avoid unit tests because Spark jobs are distributed  
    D. Hard-code all input paths inside transformation functions  

37. What is the Write-Audit-Publish (WAP) pattern?
    A. Write data to a non-consumer location, audit it, then publish it for downstream readers  
    B. Write directly to production, avoid checks, then archive logs  
    C. Write only metadata and never publish data files  
    D. Audit old data first, delete it, then write a replacement table manually  

38. What does AWS Glue primarily provide for Spark-based ETL?
    A. A managed, serverless environment for running ETL jobs without managing servers  
    B. A desktop-only spreadsheet editor  
    C. A replacement for version control  
    D. A visualization tool that cannot run code  

39. What is the role of the AWS Glue Data Catalog?
    A. It stores metadata such as schemas, locations, and formats for data assets  
    B. It stores only CI/CD runner logs  
    C. It provisions EC2 instances from Terraform modules  
    D. It replaces all data files with images  

40. What do AWS Glue Crawlers do?
    A. Scan data sources, infer schemas, and populate or update the Glue Data Catalog  
    B. Execute Git commits after every Spark action  
    C. Rewrite Python tests into Terraform  
    D. Create masked GitLab variables  

41. What is the main idea of a data lakehouse?
    A. Combine low-cost data lake storage with table management features associated with data warehouses  
    B. Store all data only in application memory  
    C. Replace analytical queries with manual file browsing  
    D. Remove metadata from the data platform  

42. Which set names the main open lakehouse table format contenders discussed in class?
    A. Apache Iceberg, Delta Lake, and Apache Hudi  
    B. GitLab, GitHub, and Bitbucket  
    C. Terraform, Ansible, and CloudFormation  
    D. CSV, TXT, and XML  

43. In Apache Iceberg, what is the role of metadata and manifest files?
    A. They track table state, schemas, snapshots, and data file statistics so engines can plan reads and writes efficiently  
    B. They store only user passwords  
    C. They replace all Parquet data files with Python objects  
    D. They are used only for Git branch naming  

44. Which Iceberg feature enables querying a table as it existed at an earlier point?
    A. Time travel through snapshots  
    B. GitLab artifacts  
    C. Terraform locals  
    D. Python context managers  

45. Why can Iceberg support column renaming without rewriting all data files?
    A. It tracks schema information using metadata and stable field identities rather than relying only on physical column names  
    B. It stores every column twice  
    C. It disables schema checks  
    D. It converts Parquet files into CSV files  

46. In GitLab CI/CD, what is the purpose of the needs keyword?
    A. To define job dependencies so jobs can run in an order based on required predecessors, not only stage order  
    B. To store cloud provider credentials in source code  
    C. To rename a Git branch after every commit  
    D. To disable all artifacts from previous jobs  

47. Why are artifacts useful in a CI/CD pipeline?
    A. They preserve outputs from one job or stage so later jobs can use them  
    B. They make every job run on the developer laptop  
    C. They replace all test reports with environment variables  
    D. They prevent runners from executing jobs  

48. What is the basic Terraform workflow emphasized in class?
    A. Write, plan, apply  
    B. Commit, merge, revert  
    C. Extract, transform, collect  
    D. Broadcast, shuffle, sort  

