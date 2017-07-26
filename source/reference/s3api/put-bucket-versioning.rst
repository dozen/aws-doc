[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api put-bucket-versioning:


*********************
put-bucket-versioning
*********************



===========
Description
===========

Sets the versioning state of an existing bucket. To set the versioning state, you must be the bucket owner.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/s3-2006-03-01/PutBucketVersioning>`_


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
  [--generate-cli-skeleton <value>]




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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

The following command enables versioning on a bucket named ``my-bucket``::

  aws s3api put-bucket-versioning --bucket my-bucket --versioning-configuration Status=Enabled

The following command enables versioning, and uses an mfa code ::

  aws s3api put-bucket-versioning --bucket my-bucket --versioning-configuration Status=Enabled --mfa "SERIAL 123456"


======
Output
======

None