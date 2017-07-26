[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api head-bucket:


***********
head-bucket
***********



===========
Description
===========

This operation is useful to determine if a bucket exists and you have permission to access it.

========
Synopsis
========

::

    head-bucket
  --bucket <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--bucket`` (string)


``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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