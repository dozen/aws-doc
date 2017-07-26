[ :ref:`aws <cli:aws>` . :ref:`redshift <cli:aws redshift>` ]

.. _cli:aws redshift enable-logging:


**************
enable-logging
**************



===========
Description
===========



Starts logging information, such as queries and connection attempts, for the specified Amazon Redshift cluster.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/redshift-2012-12-01/EnableLogging>`_


========
Synopsis
========

::

    enable-logging
  --cluster-identifier <value>
  --bucket-name <value>
  [--s3-key-prefix <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cluster-identifier`` (string)


  The identifier of the cluster on which logging is to be started.

   

  Example: ``examplecluster``  

  

``--bucket-name`` (string)


  The name of an existing S3 bucket where the log files are to be stored.

   

  Constraints:

   

   
  * Must be in the same region as the cluster 
   
  * The cluster must have read bucket and put object permissions 
   

  

``--s3-key-prefix`` (string)


  The prefix applied to the log file names.

   

  Constraints:

   

   
  * Cannot exceed 512 characters 
   
  * Cannot contain spaces( ), double quotes ("), single quotes ('), a backslash (\), or control characters. The hexadecimal codes for invalid characters are:  

     
    * x00 to x20 
     
    * x22 
     
    * x27 
     
    * x5c 
     
    * x7f or larger 
     

   
   

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

LoggingEnabled -> (boolean)

  

   ``true`` if logging is on, ``false`` if logging is off.

  

  

BucketName -> (string)

  

  The name of the S3 bucket where the log files are stored.

  

  

S3KeyPrefix -> (string)

  

  The prefix applied to the log file names.

  

  

LastSuccessfulDeliveryTime -> (timestamp)

  

  The last time that logs were delivered.

  

  

LastFailureTime -> (timestamp)

  

  The last time when logs failed to be delivered.

  

  

LastFailureMessage -> (string)

  

  The message indicating that logs failed to be delivered.

  

  

