[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api put-bucket-versioning:


*********************
put-bucket-versioning
*********************



===========
Description
===========

Sets the versioning state of an existing bucket. To set the versioning state, you must be the bucket owner.

========
Synopsis
========

::

    put-bucket-versioning
  --bucket <value>
  [--content-md5 <value>]
  [--mfa <value>]
  --versioning-configuration <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--bucket`` (string)


``--content-md5`` (string)


``--mfa`` (string)
The concatenation of the authentication device's serial number, a space, and the value that is displayed on your authentication device.

``--versioning-configuration`` (structure)




Shorthand Syntax::

    MFADelete=string,Status=string




JSON Syntax::

  {
    "MFADelete": "Enabled"|"Disabled",
    "Status": "Enabled"|"Suspended"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

The following command enables versioning on a bucket named ``my-bucket``::

  aws s3api put-bucket-versioning --bucket my-bucket --versioning-configuration Status=Enabled


======
Output
======

None