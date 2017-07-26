[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api head-bucket:


***********
head-bucket
***********



===========
Description
===========

This operation is useful to determine if a bucket exists and you have permission to access it.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/s3-2006-03-01/HeadBucket>`_


========
Synopsis
========

::

    head-bucket
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

The following command verifies access to a bucket named ``my-bucket``::

  aws s3api head-bucket --bucket my-bucket

If the bucket exists and you have access to it, no output is returned. Otherwise, an error message will be shown. For example::

  A client error (404) occurred when calling the HeadBucket operation: Not Found

======
Output
======

None