[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam get-user-policy:


***************
get-user-policy
***************



===========
Description
===========



Retrieves the specified inline policy document that is embedded in the specified IAM user.

 

.. note::

   

  Policies returned by this API are URL-encoded compliant with `RFC 3986 <https://tools.ietf.org/html/rfc3986>`_ . You can use a URL decoding method to convert the policy back to plain JSON text. For example, if you use Java, you can use the ``decode`` method of the ``java.net.URLDecoder`` utility class in the Java SDK. Other languages and SDKs provide similar functionality.

   

 

An IAM user can also have managed policies attached to it. To retrieve a managed policy document that is attached to a user, use  get-policy to determine the policy's default version, then use  get-policy-version to retrieve the policy document.

 

For more information about policies, see `Managed Policies and Inline Policies <http://docs.aws.amazon.com/IAM/latest/UserGuide/policies-managed-vs-inline.html>`_ in the *IAM User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/GetUserPolicy>`_


========
Synopsis
========

::

    get-user-policy
  --user-name <value>
  --policy-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--user-name`` (string)


  The name of the user who the policy is associated with.

   

  This parameter allows (per its `regex pattern <http://wikipedia.org/wiki/regex>`_ ) a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

  

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

**To list policy details for an IAM user**

The following ``get-user-policy`` command lists the details of the specified policy that is attached to the IAM user named ``Bob``::

  aws iam get-user-policy --user-name Bob --policy-name ExamplePolicy

Output::

  {
      "UserName": "Bob",
      "PolicyName": "ExamplePolicy",
      "PolicyDocument": {
          "Version": "2012-10-17",
          "Statement": [
              {
                  "Action": "*",
                  "Resource": "*",
                  "Effect": "Allow"
              }
          ]
      }
  }

To get a list of policies for an IAM user, use the ``list-user-policies`` command.

For more information, see `Adding a New User to Your AWS Account`_ in the *Using IAM* guide.

.. _`Adding a New User to Your AWS Account`: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_SettingUpUser.html







======
Output
======

UserName -> (string)

  

  The user the policy is associated with.

  

  

PolicyName -> (string)

  

  The name of the policy.

  

  

PolicyDocument -> (string)

  

  The policy document.

  

  

