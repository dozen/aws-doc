[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api get-bucket-location:


*******************
get-bucket-location
*******************



===========
Description
===========

Returns the region the bucket resides in.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/s3-2006-03-01/GetBucketLocation>`_


========
Synopsis
========

::

    get-bucket-location
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

The following command retrieves the location constraint for a bucket named ``my-bucket``, if a constraint exists::

  aws s3api get-bucket-location --bucket my-bucket

Output::

  {
      "LocationConstraint": "us-west-2"
  }

======
Output
======

LocationConstraint -> (string)

  

  

