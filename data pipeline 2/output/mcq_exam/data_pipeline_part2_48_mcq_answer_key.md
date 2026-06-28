# Data Pipeline Part 2 - MCQ Answer Key

## Key With Rationales

| Q | Answer | Rationale |
|---|---|---|
| 1 | B | The course focuses on engineering production-style data pipelines, including ETL, Spark, Glue, IaC, and CI/CD. |
| 2 | B | The lecture presents the lifecycle as ideation and experimentation, development, industrialization, and monitoring. |
| 3 | A | Interfaces let components interact through stable contracts rather than private implementation details. |
| 4 | A | Data modelling designs structured data representations for storage, management, and analysis. |
| 5 | A | Conceptual modelling captures business concepts, logical modelling structures relationships, and physical modelling maps to storage. |
| 6 | A | OLTP is transactional and integrity-focused; OLAP is analytical and decision-support focused. |
| 7 | A | A star schema has a central fact table directly connected to dimension tables. |
| 8 | A | A snowflake schema normalizes dimensions into additional related tables. |
| 9 | A | 1NF requires atomic values and removes repeating groups from a single cell. |
| 10 | A | 2NF removes partial dependencies from tables with composite keys. |
| 11 | A | 3NF removes transitive dependencies between non-key attributes. |
| 12 | A | Normalization is useful when data integrity and reducing anomalies matter. |
| 13 | A | SCDs are dimension attributes whose values change over time and need modelling choices. |
| 14 | A | Fact tables hold measurable events or metrics and link to dimensions. |
| 15 | A | Bucketing can place rows with the same join key together, reducing shuffle cost. |
| 16 | A | DatelistInt encodes activity across days into an integer, enabling efficient bitwise operations. |
| 17 | A | The problem refers to skew or hot keys where a small slice of data receives disproportionate load. |
| 18 | A | Idempotent operations can be retried on the same input without creating extra target-side effects. |
| 19 | A | Stateless functions are easier to test and compose because they avoid hidden mutable state. |
| 20 | A | Factories help select concrete implementations for pipelines sharing a common structure. |
| 21 | A | Strategy encapsulates interchangeable algorithms behind a common interface. |
| 22 | A | Context managers reliably release resources even if errors occur. |
| 23 | A | Dataclasses make data structure explicit and typed, unlike deeply nested unstructured containers. |
| 24 | A | Dependency injection passes external dependencies in, reducing hard-coding and improving testability. |
| 25 | A | Premature optimization means tuning before the real bottleneck or requirement is known. |
| 26 | A | MapReduce divides distributed work into map and reduce phases. |
| 27 | A | Spark improves many workloads through in-memory computation and a richer execution model. |
| 28 | A | An RDD is an immutable distributed collection processed in parallel. |
| 29 | A | Spark records transformations and executes them only when an action triggers computation. |
| 30 | A | A filter is usually narrow because each output partition depends on at most one input partition. |
| 31 | A | Wide transformations are expensive because they frequently require network shuffle. |
| 32 | A | Broadcast joins send a small dataset to executors to avoid shuffling a large side. |
| 33 | A | Shuffle hash joins repartition by key and build a hash table from the smaller side. |
| 34 | A | Sort-merge joins shuffle, sort both sides, then merge matching keys. |
| 35 | A | collect() brings data to the driver, which can exceed driver memory. |
| 36 | A | PySpark tests are easier when transformations are modular and dependencies can be injected. |
| 37 | A | WAP writes to a non-consumer location, audits quality, then publishes to downstream readers. |
| 38 | A | Glue offers managed, serverless Spark-based ETL execution. |
| 39 | A | The Glue Data Catalog stores metadata such as schemas, locations, and formats. |
| 40 | A | Crawlers infer schemas from data sources and update the catalog. |
| 41 | A | Lakehouses combine data lake storage economics with table management capabilities. |
| 42 | A | The lecture names Iceberg, Delta Lake, and Hudi as the main contenders. |
| 43 | A | Iceberg metadata and manifests track table state and file-level statistics for efficient planning. |
| 44 | A | Iceberg snapshots enable time travel to previous table states. |
| 45 | A | Iceberg uses metadata and stable field identities so renames do not require rewriting all files. |
| 46 | A | needs defines job dependencies, allowing dependency-based execution beyond simple stage order. |
| 47 | A | Artifacts pass outputs such as reports or build products between jobs or stages. |
| 48 | A | The Terraform workflow emphasized is write, plan, apply. |

## Topic Balance

| Area | Questions |
|---|---:|
| Course framing, product lifecycle, and interfaces | 1-3 |
| Data modelling, normalization, dimensional modelling, skew | 4-17 |
| Coding patterns, testability, and maintainability | 18-25 |
| Spark computational model, joins, and testing | 26-37 |
| AWS Glue, lakehouse, and Apache Iceberg | 38-45 |
| GitLab CI/CD | 46-47 |
| Terraform and IaC | 48 |

