**Netflix-Style Streaming Data Platform (AWS)**

This architecture represents a cloud-native data pipeline for a large-scale media streaming platform. The design demonstrates how cloud services can be used to build a scalable data platform for analytics and machine learning.

**Technologies Used**

**_Data Ingestion_**

- Amazon Kinesis

**_Storage_**

- Amazon S3 (Data Lake)

- Amazon RDS (Operational Data)

- Amazon Redshift (Data Warehouse)

**_Processing_**

- AWS Glue

- Amazon EMR

**_Machine Learning_**

- Amazon SageMaker

- Analytics

- Amazon QuickSight

- Architecture Diagram

**Example Data Flow**

1.	Amazon Kinesis (Ingestion Layer): Used for high-speed streaming. Captures the data from various sources: logs, clickstreams, user events 

2.	Amazon RDS (OLTP Storage Layer): Amazon RDS is a managed service designed to simplify the setup and scaling of relational databases in the cloud, helping Netflix optimize their total cost of ownership. 

3.	Amazon S3 (Data Lake- Primary Storage Layer): This is where everything arrives first. Amazon S3 The central repository or Data Lake that stores massive volumes of raw logs and video assets.

4.	Amazon Elastic Map Reduce (Processing Layer): Used to run data processing and transformation. The EMR transforms the data (from Amazon S3) and sends it to Amazon Redshift.

5.	AWS Glue: ETL process to transform the Netflix data (e.g. calculating monthly totals) and sends it over to the data warehouse (Amazon Redshift).

6.	Amazon Redshift (OLAP Storage Layer): The Data Warehouse is where structured data is stored for complex SQL Analytics and Business Intelligence. This would be ideal for calculating Netflix style metrics “What is the average watch time per genre”. Amazon Redshift will be used as their OLAP. Amazon Sage Maker will run off of Redshift.

7.	Amazon SageMaker (Machine Learning): A service that allows data scientists and developers to quickly build, train, and deploy machine learning (ML) models at any scale (Amazon Web Services, n.d.). Netflix will build specialized style algorithms such as a specialized recommendation engine and perhaps even a user churn predictor. Sage maker is also better suited for heavy data work that data scientists require. Ideally, we will build models in Sage Maker and use Amazon Quick Sight for visualization.

8.	Amazon Quick Sight (BI & Analytics): This will be used for our Business Intelligence (Amazon Web Services, n.d.). Here we will create interactive dashboards and visualizations that enable stakeholders to explore data and gain actionable insights.

