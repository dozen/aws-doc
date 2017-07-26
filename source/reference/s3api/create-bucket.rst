[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api create-bucket:


*************
create-bucket
*************



===========
Description
===========

Creates a new bucket.

========
Synopsis
========

::

    create-bucket
  [--acl <value>]
  --bucket <value>
  [--create-bucket-configuration <value>]
  [--grant-full-control <value>]
  [--grant-read <value>]
  [--grant-read-acp <value>]
  [--grant-write <value>]
  [--grant-write-acp <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--acl`` (string)
The canned ACL to apply to the bucket.

  Possible values:

  
  *   ``private``

  
  *   ``public-read``

  
  *   ``public-read-write``

  
  *   ``authenticated-read``

  

  

``--bucket`` (string)


``--create-bucket-configuration`` (structure)




Shorthand Syntax::

    LocationConstraint=string




JSON Syntax::

  {
    "LocationConstraint": "EU"|"eu-west-1"|"us-west-1"|"us-west-2"|"ap-southeast-1"|"ap-southeast-2"|"ap-northeast-1"|"sa-east-1"|"cn-north-1"|"eu-central-1"
  }



``--grant-full-control`` (string)
Allows grantee the read, write, read ACP, and write ACP permissions on the bucket.

``--grant-read`` (string)
Allows grantee to list the objects in the bucket.

``--grant-read-acp`` (string)
Allows grantee to read the bucket ACL.

``--grant-write`` (string)
Allows grantee to create, overwrite, and delete any object in the bucket.

``--grant-write-acp`` (string)
Allows grantee to write the ACL for the applicable bucket.

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

The following command creates a bucket named ``my-bucket``::

  aws s3api create-bucket --bucket my-bucket --region us-east-1

Output::

  {
      "Location": "/my-bucket"
  }


The following command creates a bucket named ``my-bucket`` in the
``eu-west-1`` region. Regions outside of ``us-east-1`` require the appropriate
``LocationConstraint`` to be specified in order to create the bucket in the
desired region::

    $ aws s3api create-bucket --bucket my-bucket --region eu-west-1 --create-bucket-configuration LocationConstraint=eu-west-1 


Output::

    {
        "Location": "http://my-bucket.s3.amazonaws.com/"
    }


======
Output
======

Location -> (string)

  

  

