[ :ref:`aws <cli:aws>` . :ref:`marketplacecommerceanalytics <cli:aws marketplacecommerceanalytics>` ]

.. _cli:aws marketplacecommerceanalytics generate-data-set:


*****************
generate-data-set
*****************



===========
Description
===========

Given a data set type and data set publication date, asynchronously publishes the requested data set to the specified S3 bucket and notifies the specified SNS topic once the data is available. Returns a unique request identifier that can be used to correlate requests with notifications from the SNS topic. Data sets will be published in comma-separated values (CSV) format with the file name {data_set_type}_YYYY-MM-DD.csv. If a file with the same name already exists (e.g. if the same data set is requested twice), the original file will be overwritten by the new file. Requires a Role with an attached permissions policy providing Allow permissions for the following actions: s3:PutObject, s3:GetBucketLocation, sns:GetTopicAttributes, sns:Publish, iam:GetRolePolicy.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/marketplacecommerceanalytics-2015-07-01/GenerateDataSet>`_


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
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--data-set-type`` (string)


  The desired data set type.

   

   

   
  * customer_subscriber_hourly_monthly_subscriptions From 2014-07-21 to present: Available daily by 5:00 PM Pacific Time. 
   
  * customer_subscriber_annual_subscriptions From 2014-07-21 to present: Available daily by 5:00 PM Pacific Time. 
   
  * daily_business_usage_by_instance_type From 2015-01-26 to present: Available daily by 5:00 PM Pacific Time. 
   
  * daily_business_fees From 2015-01-26 to present: Available daily by 5:00 PM Pacific Time. 
   
  * daily_business_free_trial_conversions From 2015-01-26 to present: Available daily by 5:00 PM Pacific Time. 
   
  * daily_business_new_instances From 2015-01-26 to present: Available daily by 5:00 PM Pacific Time. 
   
  * daily_business_new_product_subscribers From 2015-01-26 to present: Available daily by 5:00 PM Pacific Time. 
   
  * daily_business_canceled_product_subscribers From 2015-01-26 to present: Available daily by 5:00 PM Pacific Time. 
   
  * monthly_revenue_billing_and_revenue_data From 2015-02 to 2017-06: Available monthly on the 4th day of the month by 5:00pm Pacific Time. Data includes metered transactions (e.g. hourly) from two months prior. From 2017-07 to present: Available monthly on the 15th day of the month by 5:00pm Pacific Time. Data includes metered transactions (e.g. hourly) from one month prior. 
   
  * monthly_revenue_annual_subscriptions From 2015-02 to 2017-06: Available monthly on the 4th day of the month by 5:00pm Pacific Time. Data includes up-front software charges (e.g. annual) from one month prior. From 2017-07 to present: Available monthly on the 15th day of the month by 5:00pm Pacific Time. Data includes up-front software charges (e.g. annual) from one month prior. 
   
  * disbursed_amount_by_product From 2015-01-26 to present: Available every 30 days by 5:00 PM Pacific Time. 
   
  * disbursed_amount_by_product_with_uncollected_funds From 2012-04-19 to 2015-01-25: Available every 30 days by 5:00 PM Pacific Time. From 2015-01-26 to present: This data set was split into three data sets: disbursed_amount_by_product, disbursed_amount_by_age_of_uncollected_funds, and disbursed_amount_by_age_of_disbursed_funds. 
   
  * disbursed_amount_by_instance_hours From 2012-09-04 to present: Available every 30 days by 5:00 PM Pacific Time. 
   
  * disbursed_amount_by_customer_geo From 2012-04-19 to present: Available every 30 days by 5:00 PM Pacific Time. 
   
  * disbursed_amount_by_age_of_uncollected_funds From 2015-01-26 to present: Available every 30 days by 5:00 PM Pacific Time. 
   
  * disbursed_amount_by_age_of_disbursed_funds From 2015-01-26 to present: Available every 30 days by 5:00 PM Pacific Time. 
   
  * customer_profile_by_industry From 2015-10-01 to 2017-06-29: Available daily by 5:00 PM Pacific Time. From 2017-06-30 to present: This data set is no longer available. 
   
  * customer_profile_by_revenue From 2015-10-01 to 2017-06-29: Available daily by 5:00 PM Pacific Time. From 2017-06-30 to present: This data set is no longer available. 
   
  * customer_profile_by_geography From 2015-10-01 to 2017-06-29: Available daily by 5:00 PM Pacific Time. From 2017-06-30 to present: This data set is no longer available. 
   
  * sales_compensation_billed_revenue From 2016-12 to 2017-06: Available monthly on the 4th day of the month by 5:00pm Pacific Time. Data includes metered transactions (e.g. hourly) from two months prior, and up-front software charges (e.g. annual) from one month prior. From 2017-06 to present: Available monthly on the 15th day of the month by 5:00pm Pacific Time. Data includes metered transactions (e.g. hourly) from one month prior, and up-front software charges (e.g. annual) from one month prior. 
   
  * us_sales_and_use_tax_records From 2017-02-15 to present: Available monthly on the 15th day of the month by 5:00 PM Pacific Time. 
   

   

  

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

  
  *   ``disbursed_amount_by_instance_hours``

  
  *   ``disbursed_amount_by_customer_geo``

  
  *   ``disbursed_amount_by_age_of_uncollected_funds``

  
  *   ``disbursed_amount_by_age_of_disbursed_funds``

  
  *   ``customer_profile_by_industry``

  
  *   ``customer_profile_by_revenue``

  
  *   ``customer_profile_by_geography``

  
  *   ``sales_compensation_billed_revenue``

  
  *   ``us_sales_and_use_tax_records``

  

  

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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

dataSetRequestId -> (string)

  A unique identifier representing a specific request to the generate-data-set operation. This identifier can be used to correlate a request with notifications from the SNS topic.

  

