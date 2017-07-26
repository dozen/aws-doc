[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api get-bucket-acl:


**************
get-bucket-acl
**************



===========
Description
===========

Gets the access control policy for the bucket.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/s3-2006-03-01/GetBucketAcl>`_


========
Synopsis
========

::

    get-bucket-acl
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

The following command retrieves the access control list for a bucket named ``my-bucket``::

  aws s3api get-bucket-acl --bucket my-bucket

Output::

  {
      "Owner": {
          "DisplayName": "my-username",
          "ID": "7009a8971cd538e11f6b6606438875e7c86c5b672f46db45460ddcd087d36c32"
      },
      "Grants": [
          {
              "Grantee": {
                  "DisplayName": "my-username",
                  "ID": "7009a8971cd538e11f6b6606438875e7c86c5b672f46db45460ddcd087d36c32"
              },
              "Permission": "FULL_CONTROL"
          }
      ]
  }


======
Output
======

Owner -> (structure)

  

  DisplayName -> (string)

    

    

  ID -> (string)

    

    

  

Grants -> (list)

  A list of grants.

  (structure)

    

    Grantee -> (structure)

      

      DisplayName -> (string)

        Screen name of the grantee.

        

      EmailAddress -> (string)

        Email address of the grantee.

        

      ID -> (string)

        The canonical user ID of the grantee.

        

      Type -> (string)

        Type of grantee

        

      URI -> (string)

        URI of the grantee group.

        

      

    Permission -> (string)

      Specifies the permission given to the grantee.

      

    

  

