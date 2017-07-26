[ :ref:`aws <cli:aws>` . :ref:`marketplacecommerceanalytics <cli:aws marketplacecommerceanalytics>` ]

.. _cli:aws marketplacecommerceanalytics start-support-data-export:


*************************
start-support-data-export
*************************



===========
Description
===========

Given a data set type and a from date, asynchronously publishes the requested customer support data to the specified S3 bucket and notifies the specified SNS topic once the data is available. Returns a unique request identifier that can be used to correlate requests with notifications from the SNS topic. Data sets will be published in comma-separated values (CSV) format with the file name {data_set_type}_YYYY-MM-DD'T'HH-mm-ss'Z'.csv. If a file with the same name already exists (e.g. if the same data set is requested twice), the original file will be overwritten by the new file. Requires a Role with an attached permissions policy providing Allow permissions for the following actions: s3:PutObject, s3:GetBucketLocation, sns:GetTopicAttributes, sns:Publish, iam:GetRolePolicy.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/marketplacecommerceanalytics-2015-07-01/StartSupportDataExport>`_


========
Synopsis
========

::

    start-support-data-export
  --data-set-type <value>
  --from-date <value>
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


  Specifies the data set type to be written to the output csv file. The data set types customer_support_contacts_data and test_customer_support_contacts_data both result in a csv file containing the following fields: Product Id, Product Code, Customer Guid, Subscription Guid, Subscription Start Date, Organization, AWS Account Id, Given Name, Surname, Telephone Number, Email, Title, Country Code, ZIP Code, Operation Type, and Operation Time. 

   

   

   
  * *customer_support_contacts_data* Customer support contact data. The data set will contain all changes (Creates, Updates, and Deletes) to customer support contact data from the date specified in the from_date parameter.
   
  * *test_customer_support_contacts_data* An example data set containing static test data in the same format as customer_support_contacts_data
   

   

  

  Possible values:

  
  *   ``customer_support_contacts_data``

  
  *   ``test_customer_support_contacts_data``

  

  

``--from-date`` (timestamp)
The start date from which to retrieve the data set in UTC. This parameter only affects the customer_support_contacts_data data set type.

``--role-name-arn`` (string)
The Amazon Resource Name (ARN) of the Role with an attached permissions policy to interact with the provided AWS services.

``--destination-s3-bucket-name`` (string)
The name (friendly name, not ARN) of the destination S3 bucket.

``--destination-s3-prefix`` (string)
(Optional) The desired S3 prefix for the published data set, similar to a directory path in standard file systems. For example, if given the bucket name "mybucket" and the prefix "myprefix/mydatasets", the output file "outputfile" would be published to "s3://mybucket/myprefix/mydatasets/outputfile". If the prefix directory structure does not exist, it will be created. If no prefix is provided, the data set will be published to the S3 bucket root.

``--sns-topic-arn`` (string)
Amazon Resource Name (ARN) for the SNS Topic that will be notified when the data set has been published or if an error has occurred.

``--customer-defined-values`` (map)
(Optional) Key-value pairs which will be returned, unmodified, in the Amazon SNS notification message and the data set metadata file.



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

  A unique identifier representing a specific request to the start-support-data-export operation. This identifier can be used to correlate a request with notifications from the SNS topic.

  

