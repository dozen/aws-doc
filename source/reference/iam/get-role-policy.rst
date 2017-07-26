[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam get-role-policy:


***************
get-role-policy
***************



===========
Description
===========



Retrieves the specified inline policy document that is embedded with the specified IAM role.

 

.. note::

   

  Policies returned by this API are URL-encoded compliant with `RFC 3986 <https://tools.ietf.org/html/rfc3986>`_ . You can use a URL decoding method to convert the policy back to plain JSON text. For example, if you use Java, you can use the ``decode`` method of the ``java.net.URLDecoder`` utility class in the Java SDK. Other languages and SDKs provide similar functionality.

   

 

An IAM role can also have managed policies attached to it. To retrieve a managed policy document that is attached to a role, use  get-policy to determine the policy's default version, then use  get-policy-version to retrieve the policy document.

 

For more information about policies, see `Managed Policies and Inline Policies <http://docs.aws.amazon.com/IAM/latest/UserGuide/policies-managed-vs-inline.html>`_ in the *IAM User Guide* .

 

For more information about roles, see `Using Roles to Delegate Permissions and Federate Identities <http://docs.aws.amazon.com/IAM/latest/UserGuide/roles-toplevel.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/GetRolePolicy>`_


========
Synopsis
========

::

    get-role-policy
  --role-name <value>
  --policy-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--role-name`` (string)


  The name of the role associated with the policy.

   

  This parameter allows (per its `regex pattern <http://wikipedia.org/wiki/regex>`_ ) a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: _+=,.@-

  

``--policy-name`` (string)


  The name of the policy document to get.

   

  This parameter allows (per its `regex pattern <http://wikipedia.org/wiki/regex>`_ ) a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To get information about a policy attached to an IAM role**

The following ``get-role-policy`` command gets information about the specified policy attached to the role named ``Test-Role``::

  aws iam get-role-policy --role-name Test-Role --policy-name ExamplePolicy

Output::

    {
      "RoleName": "Test-Role",
      "PolicyDocument": {
          "Statement": [
              {
                  "Action": [
                      "s3:ListBucket",
                      "s3:Put*",
                      "s3:Get*",
                      "s3:*MultipartUpload*"
                  ],
                  "Resource": "*",
                  "Effect": "Allow",
                  "Sid": "1"
              }
          ]
      }
      "PolicyName": "ExamplePolicy"
    }

For more information, see `Creating a Role`_ in the *Using IAM* guide.

.. _`Creating a Role`: http://docs.aws.amazon.com/IAM/latest/UserGuide/creating-role.html



======
Output
======

RoleName -> (string)

  

  The role the policy is associated with.

  

  

PolicyName -> (string)

  

  The name of the policy.

  

  

PolicyDocument -> (string)

  

  The policy document.

  

  

