[ :ref:`aws <cli:aws>` . :ref:`marketplacecommerceanalytics <cli:aws marketplacecommerceanalytics>` ]

.. _cli:aws marketplacecommerceanalytics generate-data-set:


*****************
generate-data-set
*****************



===========
Description
===========

Given a data set type and data set publication date, asynchronously publishes the requested data set to the specified S3 bucket and notifies the specified SNS topic once the data is available. Returns a unique request identifier that can be used to correlate requests with notifications from the SNS topic. Data sets will be published in comma-separated values (CSV) format with the file name {data_set_type}_YYYY-MM-DD.csv. If a file with the same name already exists (e.g. if the same data set is requested twice), the original file will be overwritten by the new file. Requires a Role with an attached permissions policy providing Allow permissions for the following actions: s3:PutObject, s3:GetBucketLocation, sns:GetTopicAttributes, sns:Publish, iam:GetRolePolicy.

========
Synopsis
========

::

    generate-data-set
  --data-set-type <value>
  --data-set-publication-date <value>
  --role-name-arn <value>
  --destination-s3-bucket-name <value>
  [--destination-s3-prefix <value>]
  --sns-topic-arn <value>
  [--customer-defined-values <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--data-set-type`` (string)


  The desired data set type.

   

   

   
  * *customer_subscriber_hourly_monthly_subscriptions* - Available daily by 5:00 PM Pacific Time since 2014-07-21.
   
  * *customer_subscriber_annual_subscriptions* - Available daily by 5:00 PM Pacific Time since 2014-07-21.
   
  * *daily_business_usage_by_instance_type* - Available daily by 5:00 PM Pacific Time since 2015-01-26.
   
  * *daily_business_fees* - Available daily by 5:00 PM Pacific Time since 2015-01-26.
   
  * *daily_business_free_trial_conversions* - Available daily by 5:00 PM Pacific Time since 2015-01-26.
   
  * *daily_business_new_instances* - Available daily by 5:00 PM Pacific Time since 2015-01-26.
   
  * *daily_business_new_product_subscribers* - Available daily by 5:00 PM Pacific Time since 2015-01-26.
   
  * *daily_business_canceled_product_subscribers* - Available daily by 5:00 PM Pacific Time since 2015-01-26.
   
  * *monthly_revenue_billing_and_revenue_data* - Available monthly on the 4th day of the month by 5:00 PM Pacific Time since 2015-02.
   
  * *monthly_revenue_annual_subscriptions* - Available monthly on the 4th day of the month by 5:00 PM Pacific Time since 2015-02.
   
  * *disbursed_amount_by_product* - Available every 30 days by 5:00 PM Pacific Time since 2015-01-26.
   
  * *disbursed_amount_by_product_with_uncollected_funds* -This data set is only available from 2012-04-19 until 2015-01-25. After 2015-01-25, this data set was split into three data sets: disbursed_amount_by_product, disbursed_amount_by_age_of_uncollected_funds, and disbursed_amount_by_age_of_disbursed_funds. 
   
  * *disbursed_amount_by_customer_geo* - Available every 30 days by 5:00 PM Pacific Time since 2012-04-19.
   
  * *disbursed_amount_by_age_of_uncollected_funds* - Available every 30 days by 5:00 PM Pacific Time since 2015-01-26.
   
  * *disbursed_amount_by_age_of_disbursed_funds* - Available every 30 days by 5:00 PM Pacific Time since 2015-01-26.
   
  * *customer_profile_by_industry* - Available daily by 5:00 PM Pacific Time since 2015-10-01.
   
  * *customer_profile_by_revenue* - Available daily by 5:00 PM Pacific Time since 2015-10-01.
   
  * *customer_profile_by_geography* - Available daily by 5:00 PM Pacific Time since 2015-10-01.
   

   

  

  Possible values:

  
  *   ``customer_subscriber_hourly_monthly_subscriptions``

  
  *   ``customer_subscriber_annual_subscriptions``

  
  *   ``daily_business_usage_by_instance_type``

  
  *   ``daily_business_fees``

  
  *   ``daily_business_free_trial_conversions``

  
  *   ``daily_business_new_instances``

  
  *   ``daily_business_new_product_subscribers``

  
  *   ``daily_business_canceled_product_subscribers``

  
  *   ``monthly_revenue_billing_and_revenue_data``

  
  *   ``monthly_revenue_annual_subscriptions``

  
  *   ``disbursed_amount_by_product``

  
  *   ``disbursed_amount_by_product_with_uncollected_funds``

  
  *   ``disbursed_amount_by_customer_geo``

  
  *   ``disbursed_amount_by_age_of_uncollected_funds``

  
  *   ``disbursed_amount_by_age_of_disbursed_funds``

  
  *   ``customer_profile_by_industry``

  
  *   ``customer_profile_by_revenue``

  
  *   ``customer_profile_by_geography``

  

  

``--data-set-publication-date`` (timestamp)
The date a data set was published. For daily data sets, provide a date with day-level granularity for the desired day. For weekly data sets, provide a date with day-level granularity within the desired week (the day value will be ignored). For monthly data sets, provide a date with month-level granularity for the desired month (the day value will be ignored).

``--role-name-arn`` (string)
The Amazon Resource Name (ARN) of the Role with an attached permissions policy to interact with the provided AWS services.

``--destination-s3-bucket-name`` (string)
The name (friendly name, not ARN) of the destination S3 bucket.

``--destination-s3-prefix`` (string)
(Optional) The desired S3 prefix for the published data set, similar to a directory path in standard file systems. For example, if given the bucket name "mybucket" and the prefix "myprefix/mydatasets", the output file "outputfile" would be published to "s3://mybucket/myprefix/mydatasets/outputfile". If the prefix directory structure does not exist, it will be created. If no prefix is provided, the data set will be published to the S3 bucket root.

``--sns-topic-arn`` (string)
Amazon Resource Name (ARN) for the SNS Topic that will be notified when the data set has been published or if an error has occurred.

``--customer-defined-values`` (map)
(Optional) Key-value pairs which will be returned, unmodified, in the Amazon SNS notification message and the data set metadata file. These key-value pairs can be used to correlated responses with tracking information from other systems.



Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

dataSetRequestId -> (string)

  A unique identifier representing a specific request to the generate-data-set operation. This identifier can be used to correlate a request with notifications from the SNS topic.

  

