[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api delete-bucket-tagging:


*********************
delete-bucket-tagging
*********************



===========
Description
===========

Deletes the tags from the bucket.

========
Synopsis
========

::

    delete-bucket-tagging
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

The following command deletes a tagging configuration from a bucket named ``my-bucket``::

  aws s3api delete-bucket-tagging --bucket my-bucket


======
Output
======

None