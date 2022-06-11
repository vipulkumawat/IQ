**Apache Nifi**

```
Changes in the Latest Apache NiFi Version 1.14.0+
Changes in the Latest Apache NiFi Version 1.14.0+

If you have downloaded the latest NiFi version 1.14.0+ then NiFi won't be accessible using http://localhost:8080/nifi

To access NiFi in this case, you have to use the HTTPS URL: https://127.0.0.1:8443/nifi

This will also prompt you to enter the Username and Password. You can get the Username and Password from the nifi-app.log file inside the /logs folder.

Kindly search for "Generated Username" & "Generated Password" to find the Username and Password for your NiFi instance.



What is a DataFlow, Data Pipeline and ETL?
DataFlow: Moving Data/content from Source to Destination
Data can be CSV, JSON, XML, HTTP data, Image, videos, Telemetry data etc.

Data Pipeline: Movement and transformation of data/conent from source to destination

Data pipeline - batch/stream
ETL - batch
Extract Transform Load


Four V's:
Volume: refers to the vast amount of data generated every second
Velocity: refers to the speed at which new data is generated and the speed at which data moves around
Variety: refers to the different types of data we can now use
Veracity: refers to the messiness or trustworthiness of the data

Considerations:
Support for multiple data formats: CSV, JSON, plaintext, images, vedios etc

Support for various types of sources and destinations - FTP, HTTP, SQL data bases, NoSQL databases, Search Engines, Cache Server etc.

Scalable And Reliable For large volume and high velocity data
You should also consider Data cleansing and Data Validation logic

Apache Nifi supports Powerful and scalable directed graphs of data routing, transformation and system mediation logic

built to automate the flow of data between systems. it can propagate any data content from any source to any destination.


Section3: Apache NiFi Basics
NiFi User Interface




https://marklogic-community.github.io/marklogic-nifi-incubator/recipes/1-2-extract-values-from-json-data%EF%BB%BF.html

https://nifi.apache.org/docs/nifi-docs/components/org.apache.nifi/nifi-record-serialization-services-nar/1.5.0/org.apache.nifi.json.JsonPathReader/additionalDetails.html


https://nifi.apache.org/docs/nifi-docs/html/expression-language-guide.html#escaping

https://nifi.apache.org/docs.html

https://stackoverflow.com/questions/52926400/apache-nifi-1-7-1-flatten-json-with-delimiter

https://www.projectpro.io/recipes/convert-multi-nested-json-files-into-denormalized-flattened-out-versions-of-csv-nifi



https://stackoverflow.com/questions/52940673/evaluatejsonpath-unable-to-return-a-scalar

Generated Username [5ecd2e1d-0cb8-4950-887f-c1e92c9d46a9]
Generated Password [9M/LzSTqXrVUQ2M7o0vBfpslfCz8hfVf]


https://community.cloudera.com/t5/Community-Articles/Stream-data-into-HIVE-like-a-Boss-using-NiFi-HiveStreaming/ta-p/247130


https://github.com/sucitw/python-script-in-NiFi
https://community.cloudera.com/t5/Community-Articles/Python-Script-in-NiFi/ta-p/246406/page/2/show-comments/true
https://github.com/sucitw/python-script-in-NiFi/blob/master/json_transform.py



```