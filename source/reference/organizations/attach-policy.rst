[ :ref:`aws <cli:aws>` . :ref:`organizations <cli:aws organizations>` ]

.. _cli:aws organizations attach-policy:


*************
attach-policy
*************



===========
Description
===========



Attaches a policy to a root, an organizational unit, or an individual account. How the policy affects accounts depends on the type of policy:

 

 
* **Service control policy (SCP)** - An SCP specifies what permissions can be delegated to users in affected member accounts. The scope of influence for a policy depends on what you attach the policy to: 

   
  * If you attach an SCP to a root, it affects all accounts in the organization. 
   
  * If you attach an SCP to an OU, it affects all accounts in that OU and in any child OUs. 
   
  * If you attach the policy directly to an account, then it affects only that account. 
   

 

SCPs essentially are permission "filters". When you attach one SCP to a higher level root or OU, and you also attach a different SCP to a child OU or to an account, the child policy can further restrict only the permissions that pass through the parent filter and are available to the child. An SCP that is attached to a child cannot grant a permission that is not already granted by the parent. For example, imagine that the parent SCP allows permissions A, B, C, D, and E. The child SCP allows C, D, E, F, and G. The result is that the accounts affected by the child SCP are allowed to use only C, D, and E. They cannot use A or B because they were filtered out by the child OU. They also cannot use F and G because they were filtered out by the parent OU. They cannot be granted back by the child SCP; child SCPs can only filter the permissions they receive from the parent SCP.

 

AWS Organizations attaches a default SCP named ``"FullAWSAccess`` to every root, OU, and account. This default SCP allows all services and actions, enabling any new child OU or account to inherit the permissions of the parent root or OU. If you detach the default policy, you must replace it with a policy that specifies the permissions that you want to allow in that OU or account.

 

For more information about how Organizations policies permissions work, see `Using Service Control Policies <http://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_scp.html>`_ in the *AWS Organizations User Guide* .

 
 

 

This operation can be called only from the organization's master account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/organizations-2016-11-28/AttachPolicy>`_


========
Synopsis
========

::

    attach-policy
  --policy-id <value>
  --target-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--policy-id`` (string)


  The unique identifier (ID) of the policy that you want to attach to the target. You can get the ID for the policy by calling the  list-policies operation.

   

  The `regex pattern <http://wikipedia.org/wiki/regex>`_ for a policy ID string requires "p-" followed by from 8 to 128 lower-case letters or digits.

  

``--target-id`` (string)


  The unique identifier (ID) of the root, OU, or account that you want to attach the policy to. You can get the ID by calling the  list-roots ,  list-organizational-units-for-parent , or  list-accounts operations.

   

  The `regex pattern <http://wikipedia.org/wiki/regex>`_ for a target ID string requires one of the following:

   

   
  * Root: a string that begins with "r-" followed by from 4 to 32 lower-case letters or digits. 
   
  * Account: a string that consists of exactly 12 digits. 
   
  * Organizational unit (OU): a string that begins with "ou-" followed by from 4 to 32 lower-case letters or digits (the ID of the root that the OU is in) followed by a second "-" dash and from 8 to 32 additional lower-case letters or digits. 
   

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To attach a policy to an OU**

The following example shows how to attach a service control policy (SCP) to an OU.

Command::

  aws organizations attach-policy --target-id ou-examplerootid111-exampleouid111 --policy-id p-examplepolicyid111

**To attach a policy directly to an AWS account**
  
The following example shows how to attach a service control policy directly to an account.

Command::

  aws organizations attach-policy --target-id 333333333333 --policy-id p-examplepolicyid111

======
Output
======

None