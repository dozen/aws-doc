[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api get-bucket-cors:


***************
get-bucket-cors
***************



===========
Description
===========

Returns the cors configuration for the bucket.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/s3-2006-03-01/GetBucketCors>`_


========
Synopsis
========

::

    get-bucket-cors
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



========
Examples
========

The following command retrieves the Cross-Origin Resource Sharing configuration for a bucket named ``my-bucket``::

  aws s3api get-bucket-cors --bucket my-bucket

Output::

  {
      "CORSRules": [
          {
              "AllowedHeaders": [
                  "*"
              ],
              "ExposeHeaders": [
                  "x-amz-server-side-encryption"
              ],
              "AllowedMethods": [
                  "PUT",
                  "POST",
                  "DELETE"
              ],
              "MaxAgeSeconds": 3000,
              "AllowedOrigins": [
                  "http://www.example.com"
              ]
          },
          {
              "AllowedHeaders": [
                  "Authorization"
              ],
              "MaxAgeSeconds": 3000,
              "AllowedMethods": [
                  "GET"
              ],
              "AllowedOrigins": [
                  "*"
              ]
          }
      ]
  }


======
Output
======

CORSRules -> (list)

  

  (structure)

    

    AllowedHeaders -> (list)

      Specifies which headers are allowed in a pre-flight OPTIONS request.

      (string)

        

        

      

    AllowedMethods -> (list)

      Identifies HTTP methods that the domain/origin specified in the rule is allowed to execute.

      (string)

        

        

      

    AllowedOrigins -> (list)

      One or more origins you want customers to be able to access the bucket from.

      (string)

        

        

      

    ExposeHeaders -> (list)

      One or more headers in the response that you want customers to be able to access from their applications (for example, from a JavaScript XMLHttpRequest object).

      (string)

        

        

      

    MaxAgeSeconds -> (integer)

      The time in seconds that your browser is to cache the preflight response for the specified resource.

      

    

  

