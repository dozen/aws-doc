[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api put-bucket-website:


******************
put-bucket-website
******************



===========
Description
===========

Set the website configuration for a bucket.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/s3-2006-03-01/PutBucketWebsite>`_


========
Synopsis
========

::

    put-bucket-website
  --bucket <value>
  [--content-md5 <value>]
  --website-configuration <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--bucket`` (string)


``--content-md5`` (string)


``--website-configuration`` (structure)




JSON Syntax::

  {
    "ErrorDocument": {
      "Key": "string"
    },
    "IndexDocument": {
      "Suffix": "string"
    },
    "RedirectAllRequestsTo": {
      "HostName": "string",
      "Protocol": "http"|"https"
    },
    "RoutingRules": [
      {
        "Condition": {
          "HttpErrorCodeReturnedEquals": "string",
          "KeyPrefixEquals": "string"
        },
        "Redirect": {
          "HostName": "string",
          "HttpRedirectCode": "string",
          "Protocol": "http"|"https",
          "ReplaceKeyPrefixWith": "string",
          "ReplaceKeyWith": "string"
        }
      }
      ...
    ]
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

The applies a static website configuration to a bucket named ``my-bucket``::

  aws s3api put-bucket-website --bucket my-bucket --website-configuration file://website.json

The file ``website.json`` is a JSON document in the current folder that specifies index and error pages for the website::

  {
      "IndexDocument": {
          "Suffix": "index.html"
      },
      "ErrorDocument": {
          "Key": "error.html"
      }
  }


======
Output
======

None