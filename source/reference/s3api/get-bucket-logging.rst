[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api get-bucket-logging:


******************
get-bucket-logging
******************



===========
Description
===========

Returns the logging status of a bucket and the permissions users have to view and modify that status. To use GET, you must be the bucket owner.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/s3-2006-03-01/GetBucketLogging>`_


========
Synopsis
========

::

    get-bucket-logging
  --bucket <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--bucket`` (string)


``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

LoggingEnabled -> (structure)

  

  TargetBucket -> (string)

    Specifies the bucket where you want Amazon S3 to store server access logs. You can have your logs delivered to any bucket that you own, including the same bucket that is being logged. You can also configure multiple buckets to deliver their logs to the same target bucket. In this case you should choose a different TargetPrefix for each source bucket so that the delivered log files can be distinguished by key.

    

  TargetGrants -> (list)

    

    (structure)

      

      Grantee -> (structure)

        

        DisplayName -> (string)

          Screen name of the grantee.

          

        EmailAddress -> (string)

          Email address of the grantee.

          

        ID -> (string)

          The canonical user ID of the grantee.

          

        Type -> (string)

          Type of grantee

          

        URI -> (string)

          URI of the grantee group.

          

        

      Permission -> (string)

        Logging permissions assigned to the Grantee for the bucket.

        

      

    

  TargetPrefix -> (string)

    This element lets you specify a prefix for the keys that the log files will be stored under.

    

  

