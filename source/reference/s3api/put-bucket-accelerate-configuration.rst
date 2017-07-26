[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api put-bucket-accelerate-configuration:


***********************************
put-bucket-accelerate-configuration
***********************************



===========
Description
===========

Sets the accelerate configuration of an existing bucket.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/s3-2006-03-01/PutBucketAccelerateConfiguration>`_


========
Synopsis
========

::

    put-bucket-accelerate-configuration
  --bucket <value>
  --accelerate-configuration <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--bucket`` (string)
Name of the bucket for which the accelerate configuration is set.

``--accelerate-configuration`` (structure)
Specifies the Accelerate Configuration you want to set for the bucket.



Shorthand Syntax::

    Status=string




JSON Syntax::

  {
    "Status": "Enabled"|"Suspended"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None