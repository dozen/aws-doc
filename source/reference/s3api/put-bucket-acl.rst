[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api put-bucket-acl:


**************
put-bucket-acl
**************



===========
Description
===========

Sets the permissions on a bucket using access control lists (ACL).

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/s3-2006-03-01/PutBucketAcl>`_


========
Synopsis
========

::

    put-bucket-acl
  [--acl <value>]
  [--access-control-policy <value>]
  --bucket <value>
  [--content-md5 <value>]
  [--grant-full-control <value>]
  [--grant-read <value>]
  [--grant-read-acp <value>]
  [--grant-write <value>]
  [--grant-write-acp <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




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

  

  

``--access-control-policy`` (structure)




JSON Syntax::

  {
    "Grants": [
      {
        "Grantee": {
          "DisplayName": "string",
          "EmailAddress": "string",
          "ID": "string",
          "Type": "CanonicalUser"|"AmazonCustomerByEmail"|"Group",
          "URI": "string"
        },
        "Permission": "FULL_CONTROL"|"WRITE"|"WRITE_ACP"|"READ"|"READ_ACP"
      }
      ...
    ],
    "Owner": {
      "DisplayName": "string",
      "ID": "string"
    }
  }



``--bucket`` (string)


``--content-md5`` (string)


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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

This example grants ``full control`` to two AWS users (*user1@example.com* and *user2@example.com*) and ``read``
permission to everyone::

   aws s3api put-bucket-acl --bucket MyBucket --grant-full-control emailaddress=user1@example.com,emailaddress=user2@example.com --grant-read uri=http://acs.amazonaws.com/groups/global/AllUsers

See http://docs.aws.amazon.com/AmazonS3/latest/API/RESTBucketPUTacl.html for details on custom ACLs (the s3api ACL
commands, such as ``put-bucket-acl``, use the same shorthand argument notation).



======
Output
======

None