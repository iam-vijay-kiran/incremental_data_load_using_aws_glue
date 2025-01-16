# incremental_data_load_using_aws_glue

* Create new s3 bucket -> telecom-data-bucket/input folder
* Aws glue -> create database telecom-catalog -> create crawler with s3 input folder location in telecom-catalog db
* Run the crawler for input metadata added in s3 input folder
* Create a glue script to read and count
* If we need incremental load I., only to read new files in bucket then we need to enable job bookmark in the ui and transaction_ctx = "s3_input_new” & at the end job.commit() in the script
* Once check the scripts developed

Observations:
* Glue job might fail due to job name arguments not given in incremental load, but the work it should do might be done, so we need to check it at cloudwatch logs despite it shows glue job run fails
