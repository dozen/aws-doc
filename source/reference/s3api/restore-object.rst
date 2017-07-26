[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api restore-object:


**************
restore-object
**************



===========
Description
===========

Restores an archived copy of an object back into Amazon S3

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
  [--generate-cli-skeleton]




=======
Options
=======

``--bucket`` (string)


``--key`` (string)


``--version-id`` (string)


``--restore-request`` (structure)




Shorthand Syntax::

    Days=integer




JSON Syntax::

  {
    "Days": integer
  }



``--request-payer`` (string)
Confirms that the requester knows that she or he will be charged for the request. Bucket owners need not specify this parameter in their requests. Documentation on downloading objects from requester pays buckets can be found at http://docs.aws.amazon.com/AmazonS3/latest/dev/ObjectsinRequesterPaysBuckets.html

  Possible values:

  
  *   ``requester``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

RequestCharged -> (string)

  If present, indicates that the requester was successfully charged for the request.

  

