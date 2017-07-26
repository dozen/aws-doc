[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api get-bucket-policy:


*****************
get-bucket-policy
*****************



===========
Description
===========

Returns the policy of a specified bucket.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/s3-2006-03-01/GetBucketPolicy>`_


========
Synopsis
========

::

    get-bucket-policy
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

The following command retrieves the bucket policy for a bucket named ``my-bucket``::

  aws s3api get-bucket-policy --bucket my-bucket

Output::

  {
      "Policy": "{\"Version\":\"2008-10-17\",\"Statement\":[{\"Sid\":\"\",\"Effect\":\"Allow\",\"Principal\":\"*\",\"Action\":\"s3:GetObject\",\"Resource\":\"arn:aws:s3:::my-bucket/*\"},{\"Sid\":\"\",\"Effect\":\"Deny\",\"Principal\":\"*\",\"Action\":\"s3:GetObject\",\"Resource\":\"arn:aws:s3:::my-bucket/secret/*\"}]}"
  }

Get and put a bucket policy
---------------------------

The following example shows how you can download an Amazon S3 bucket policy,
make modifications to the file, and then use ``put-bucket-policy`` to
apply the modified bucket policy.  To download the bucket policy to a file,
you can run::

  aws s3api get-bucket-policy --bucket mybucket --query Policy --output text > policy.json

You can then modify the ``policy.json`` file as needed.  Finally you can apply
this modified policy back to the S3 bucket by running::

  aws s3api put-bucket-policy --bucket mybucket --policy file://policy.json


======
Output
======

Policy -> (string)

  The bucket policy as a JSON document.

  

