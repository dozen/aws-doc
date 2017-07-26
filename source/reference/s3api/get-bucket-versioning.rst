[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api get-bucket-versioning:


*********************
get-bucket-versioning
*********************



===========
Description
===========

Returns the versioning state of a bucket.

========
Synopsis
========

::

    get-bucket-versioning
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

The following command retrieves the versioning configuration for a bucket named ``my-bucket``::

  aws s3api get-bucket-versioning --bucket my-bucket

Output::

  {
      "Status": "Enabled"
  }


======
Output
======

Status -> (string)

  The versioning state of the bucket.

  

MFADelete -> (string)

  Specifies whether MFA delete is enabled in the bucket versioning configuration. This element is only returned if the bucket has been configured with MFA delete. If the bucket has never been so configured, this element is not returned.

  

