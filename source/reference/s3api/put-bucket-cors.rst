[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api put-bucket-cors:


***************
put-bucket-cors
***************



===========
Description
===========

Sets the cors configuration for a bucket.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/s3-2006-03-01/PutBucketCors>`_


========
Synopsis
========

::

    put-bucket-cors
  --bucket <value>
  --cors-configuration <value>
  [--content-md5 <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--bucket`` (string)


``--cors-configuration`` (structure)




JSON Syntax::

  {
    "CORSRules": [
      {
        "AllowedHeaders": ["string", ...],
        "AllowedMethods": ["string", ...],
        "AllowedOrigins": ["string", ...],
        "ExposeHeaders": ["string", ...],
        "MaxAgeSeconds": integer
      }
      ...
    ]
  }



``--content-md5`` (string)


``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

The following example enables ``PUT``, ``POST``, and ``DELETE`` requests from *www.example.com*, and enables ``GET``
requests from any domain::

   aws s3api put-bucket-cors --bucket MyBucket --cors-configuration file://cors.json

   cors.json:
   {
     "CORSRules": [
       {
         "AllowedOrigins": ["http://www.example.com"],
         "AllowedHeaders": ["*"],
         "AllowedMethods": ["PUT", "POST", "DELETE"],
         "MaxAgeSeconds": 3000,
         "ExposeHeaders": ["x-amz-server-side-encryption"]
       },
       {
         "AllowedOrigins": ["*"],
         "AllowedHeaders": ["Authorization"],
         "AllowedMethods": ["GET"],
         "MaxAgeSeconds": 3000
       }
     ]
   }



======
Output
======

None