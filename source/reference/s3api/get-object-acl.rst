[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api get-object-acl:


**************
get-object-acl
**************



===========
Description
===========

Returns the access control list (ACL) of an object.

========
Synopsis
========

::

    get-object-acl
  --bucket <value>
  --key <value>
  [--version-id <value>]
  [--request-payer <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--bucket`` (string)


``--key`` (string)


``--version-id`` (string)
VersionId used to reference a specific version of the object.

``--request-payer`` (string)
Confirms that the requester knows that she or he will be charged for the request. Bucket owners need not specify this parameter in their requests. Documentation on downloading objects from requester pays buckets can be found at http://docs.aws.amazon.com/AmazonS3/latest/dev/ObjectsinRequesterPaysBuckets.html

  Possible values:

  
  *   ``requester``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

The following command retrieves the access control list for an object in a bucket named ``my-bucket``::

  aws s3api get-object-acl --bucket my-bucket --key index.html

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
          },
          {
              "Grantee": {
                  "URI": "http://acs.amazonaws.com/groups/global/AllUsers"
              },
              "Permission": "READ"
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

      

    

  

RequestCharged -> (string)

  If present, indicates that the requester was successfully charged for the request.

  

