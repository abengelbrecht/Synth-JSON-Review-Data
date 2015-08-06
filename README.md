Synth-JSON-Review-Data
======================

Generated JSON files for Customer reviews to test querying and analysis on complex  JSON documents. 

Also includes schema files to generate much larger data sets using Ted Dunning's log-synth tool https://github.com/tdunning/log-synth.  To generate data using the tool, use the following example command line (in this case, generate 60K business review entries):

```
java -cp target/log-synth-0.1-SNAPSHOT-jar-with-dependencies.jar com.mapr.synth.Synth -count 60000 -format JSON -schema ../Synth-JSON-Review-Data/schemas/business.schema.json
```

There are 3 file types: business, user and review. The review file(s) have key fields (business_id and user_id) that corrolates to the business_id field in the business file(s) and the user_id field in the user file(s).

A small sample set is located in the sampl-data directory with 1k records for business, 5k for user and 10k for reviews.

The schema files for all 3 are located in the schemas directory and can be used with the log-synth tool to generate larger data sets. Remember to increase the size of the foreign-keys for both business_id and user_id fields if larger record sets are used for business and user, this is very important to ensure proper correlation between the review records and the business and user records.
