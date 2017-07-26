[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api put-bucket-policy:


*****************
put-bucket-policy
*****************



===========
Description
===========

Replaces a policy on a bucket. If the bucket already has a policy, the one in this request completely replaces it.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/s3-2006-03-01/PutBucketPolicy>`_


========
Synopsis
========

::

    put-bucket-policy
  --bucket <value>
  [--content-md5 <value>]
  --policy <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--bucket`` (string)


``--content-md5`` (string)


``--policy`` (string)
The bucket policy as a JSON document.

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

This example allows all users to retrieve any object in *MyBucket* except those in the *MySecretFolder*. It also
grants ``put`` and ``delete`` permission to the root user of the AWS account ``1234-5678-9012``::

   aws s3api put-bucket-policy --bucket MyBucket --policy file://policy.json

   policy.json:
   {
      "Statement": [
         {
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::MyBucket/*"
         },
         {
            "Effect": "Deny",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::MyBucket/MySecretFolder/*"
         },
         {
            "Effect": "Allow",
            "Principal": {
               "AWS": "arn:aws:iam::123456789012:root"
            },
            "Action": [
               "s3:DeleteObject",
               "s3:PutObject"
            ],
            "Resource": "arn:aws:s3:::MyBucket/*"
         }
      ]
   }



======
Output
======

None