[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam get-role:


********
get-role
********



===========
Description
===========



Retrieves information about the specified role, including the role's path, GUID, ARN, and the role's trust policy that grants permission to assume the role. For more information about roles, see `Working with Roles <http://docs.aws.amazon.com/IAM/latest/UserGuide/WorkingWithRoles.html>`_ .

 

.. note::

   

  Policies returned by this API are URL-encoded compliant with `RFC 3986 <https://tools.ietf.org/html/rfc3986>`_ . You can use a URL decoding method to convert the policy back to plain JSON text. For example, if you use Java, you can use the ``decode`` method of the ``java.net.URLDecoder`` utility class in the Java SDK. Other languages and SDKs provide similar functionality.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/GetRole>`_


========
Synopsis
========

::

    get-role
  --role-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--role-name`` (string)


  The name of the IAM role to get information about.

   

  This parameter allows (per its `regex pattern <http://wikipedia.org/wiki/regex>`_ ) a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: _+=,.@-

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To get information about an IAM role**

The following ``get-role`` command gets information about the role named ``Test-Role``::

  aws iam get-role --role-name Test-Role

Output::

  {
    "Role": {
        "AssumeRolePolicyDocument": "<URL-encoded-JSON>",
        "RoleId": "AIDIODR4TAW7CSEXAMPLE",
        "CreateDate": "2013-04-18T05:01:58Z",
        "RoleName": "Test-Role",
        "Path": "/",
        "Arn": "arn:aws:iam::123456789012:role/Test-Role"
    }
  }

The command displays the trust policy attached to the role. To list the permissions policies attached to a role, use the ``list-role-policies`` command.

For more information, see `Creating a Role`_ in the *Using IAM* guide.

.. _`Creating a Role`: http://docs.aws.amazon.com/IAM/latest/UserGuide/creating-role.html



======
Output
======

Role -> (structure)

  

  A structure containing details about the IAM role.

  

  Path -> (string)

    

    The path to the role. For more information about paths, see `IAM Identifiers <http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html>`_ in the *Using IAM* guide. 

    

    

  RoleName -> (string)

    

    The friendly name that identifies the role.

    

    

  RoleId -> (string)

    

    The stable and unique string identifying the role. For more information about IDs, see `IAM Identifiers <http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html>`_ in the *Using IAM* guide. 

    

    

  Arn -> (string)

    

    The Amazon Resource Name (ARN) specifying the role. For more information about ARNs and how to use them in policies, see `IAM Identifiers <http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html>`_ in the *IAM User Guide* guide. 

    

    

  CreateDate -> (timestamp)

    

    The date and time, in `ISO 8601 date-time format <http://www.iso.org/iso/iso8601>`_ , when the role was created.

    

    

  AssumeRolePolicyDocument -> (string)

    

    The policy that grants an entity permission to assume the role.

    

    

  Description -> (string)

    

    A description of the role that you provide.

    

    

  

