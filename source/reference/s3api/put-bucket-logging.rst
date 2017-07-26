[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api put-bucket-logging:


******************
put-bucket-logging
******************



===========
Description
===========

Set the logging parameters for a bucket and to specify permissions for who can view and modify the logging parameters. To set the logging status of a bucket, you must be the bucket owner.

========
Synopsis
========

::

    put-bucket-logging
  --bucket <value>
  --bucket-logging-status <value>
  [--content-md5 <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--bucket`` (string)


``--bucket-logging-status`` (structure)




JSON Syntax::

  {
    "LoggingEnabled": {
      "TargetBucket": "string",
      "TargetGrants": [
        {
          "Grantee": {
            "DisplayName": "string",
            "EmailAddress": "string",
            "ID": "string",
            "Type": "CanonicalUser"|"AmazonCustomerByEmail"|"Group",
            "URI": "string"
          },
          "Permission": "FULL_CONTROL"|"READ"|"WRITE"
        }
        ...
      ],
      "TargetPrefix": "string"
    }
  }



``--content-md5`` (string)


``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

The example below sets the logging policy for *MyBucket*. The AWS user *user@example.com* will have full control over
the log files, and all users will have access to them. First, grant S3 permission with ``put-bucket-acl``::

   aws s3api put-bucket-acl --bucket MyBucket --grant-write URI=http://acs.amazonaws.com/groups/s3/LogDelivery --grant-read-acp URI=http://acs.amazonaws.com/groups/s3/LogDelivery

Then apply the logging policy::

   aws s3api put-bucket-logging --bucket MyBucket --bucket-logging-status file://logging.json

``logging.json`` is a JSON document in the current folder that contains the logging policy::

   {
     "LoggingEnabled": {
       "TargetBucket": "MyBucket",
       "TargetPrefix": "MyBucketLogs/",
       "TargetGrants": [
         {
           "Grantee": {
             "Type": "AmazonCustomerByEmail",
             "EmailAddress": "user@example.com"
           },
           "Permission": "FULL_CONTROL"
         },
         {
           "Grantee": {
             "Type": "Group",
             "URI": "http://acs.amazonaws.com/groups/global/AllUsers"
           },
           "Permission": "READ"
         }
       ]
     }
   }

.. note:: the ``put-bucket-acl`` command is required to grant S3's log delivery system the necessary permissions (write
   and read-acp permissions).


======
Output
======

None