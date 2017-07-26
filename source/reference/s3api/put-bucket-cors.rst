[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api put-bucket-cors:


***************
put-bucket-cors
***************



===========
Description
===========

Sets the cors configuration for a bucket.

========
Synopsis
========

::

    put-bucket-cors
  --bucket <value>
  --cors-configuration <value>
  [--content-md5 <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




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

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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