[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api restore-object:


**************
restore-object
**************



===========
Description
===========

Restores an archived copy of an object back into Amazon S3

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/s3-2006-03-01/RestoreObject>`_


========
Synopsis
========

::

    restore-object
  --bucket <value>
  --key <value>
  [--version-id <value>]
  [--restore-request <value>]
  [--request-payer <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--bucket`` (string)


``--key`` (string)


``--version-id`` (string)


``--restore-request`` (structure)




Shorthand Syntax::

    Days=integer,GlacierJobParameters={Tier=string}




JSON Syntax::

  {
    "Days": integer,
    "GlacierJobParameters": {
      "Tier": "Standard"|"Bulk"|"Expedited"
    }
  }



``--request-payer`` (string)
Confirms that the requester knows that she or he will be charged for the request. Bucket owners need not specify this parameter in their requests. Documentation on downloading objects from requester pays buckets can be found at http://docs.aws.amazon.com/AmazonS3/latest/dev/ObjectsinRequesterPaysBuckets.html

  Possible values:

  
  *   ``requester``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

RequestCharged -> (string)

  If present, indicates that the requester was successfully charged for the request.

  

