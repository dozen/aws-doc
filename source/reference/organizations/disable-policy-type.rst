[ :ref:`aws <cli:aws>` . :ref:`organizations <cli:aws organizations>` ]

.. _cli:aws organizations disable-policy-type:


*******************
disable-policy-type
*******************



===========
Description
===========



Disables an organizational control policy type in a root. A poicy of a certain type can be attached to entities in a root only if that type is enabled in the root. After you perform this operation, you no longer can attach policies of the specified type to that root or to any OU or account in that root. You can undo this by using the  enable-policy-type operation.

 

This operation can be called only from the organization's master account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/organizations-2016-11-28/DisablePolicyType>`_


========
Synopsis
========

::

    disable-policy-type
  --root-id <value>
  --policy-type <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--root-id`` (string)


  The unique identifier (ID) of the root in which you want to disable a policy type. You can get the ID from the  list-policies operation.

   

  The `regex pattern <http://wikipedia.org/wiki/regex>`_ for a root ID string requires "r-" followed by from 4 to 32 lower-case letters or digits.

  

``--policy-type`` (string)


  The policy type that you want to disable in this root.

  

  Possible values:

  
  *   ``SERVICE_CONTROL_POLICY``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To disable a policy type in a root**

The following example shows how to disable the service control policy (SCP) policy type in a root. 

Command::

  aws organizations disable-policy-type --root-id r-examplerootid111 --policy-type SERVICE_CONTROL_POLICY
  
The response shows that the PolicyTypes response element for the specified root no longer includes SERVICE_CONTROL_POLICY.

Output::

  {
    "Root": {
      "PolicyTypes": [],
      "Name": "Root",
      "Id": "r-examplerootid111",
      "Arn": "arn:aws:organizations::111111111111:root/o-exampleorgid/r-examplerootid111"
    }
  }

======
Output
======

Root -> (structure)

  

  A structure that shows the root with the updated list of enabled policy types.

  

  Id -> (string)

    

    The unique identifier (ID) for the root.

     

    The `regex pattern <http://wikipedia.org/wiki/regex>`_ for a root ID string requires "r-" followed by from 4 to 32 lower-case letters or digits.

    

    

  Arn -> (string)

    

    The Amazon Resource Name (ARN) of the root.

     

    For more information about ARNs in Organizations, see `ARN Formats Supported by Organizations <http://docs.aws.amazon.com/organizations/latest/userguide/orgs_permissions.html#orgs-permissions-arns>`_ in the *AWS Organizations User Guide* .

    

    

  Name -> (string)

    

    The friendly name of the root.

     

    The `regex pattern <http://wikipedia.org/wiki/regex>`_ that is used to validate this parameter is a string of any of the characters in the ASCII character range.

    

    

  PolicyTypes -> (list)

    

    The types of policies that are currently enabled for the root and therefore can be attached to the root or to its OUs or accounts.

    

    (structure)

      

      Contains information about a policy type and its status in the associated root.

      

      Type -> (string)

        

        The name of the policy type.

        

        

      Status -> (string)

        

        The status of the policy type as it relates to the associated root. To attach a policy of the specified type to a root or to an OU or account in that root, it must be available in the organization and enabled for that root.

        

        

      

    

  

