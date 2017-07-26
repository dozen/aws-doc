[ :ref:`aws <cli:aws>` . :ref:`organizations <cli:aws organizations>` ]

.. _cli:aws organizations detach-policy:


*************
detach-policy
*************



===========
Description
===========



Detaches a policy from a target root, organizational unit, or account. If the policy being detached is a service control policy (SCP), the changes to permissions for IAM users and roles in affected accounts are immediate.

 

 **Note:** Every root, OU, and account must have at least one SCP attached. If you want to replace the default ``FullAWSAccess`` policy with one that limits the permissions that can be delegated, then you must attach the replacement policy before you can remove the default one. This is the authorization strategy of `whitelisting <http://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_about-scps.html#orgs_policies_whitelist>`_ . If you instead attach a second SCP and leave the ``FullAWSAccess`` SCP still attached, and specify ``"Effect": "Deny"`` in the second SCP to override the ``"Effect": "Allow"`` in the ``FullAWSAccess`` policy (or any other attached SCP), then you are using the authorization strategy of `blacklisting <http://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_about-scps.html#orgs_policies_blacklist>`_ . 

 

This operation can be called only from the organization's master account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/organizations-2016-11-28/DetachPolicy>`_


========
Synopsis
========

::

    detach-policy
  --policy-id <value>
  --target-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--policy-id`` (string)


  The unique identifier (ID) of the policy you want to detach. You can get the ID from the  list-policies or  list-policies-for-target operations.

   

  The `regex pattern <http://wikipedia.org/wiki/regex>`_ for a policy ID string requires "p-" followed by from 8 to 128 lower-case letters or digits.

  

``--target-id`` (string)


  The unique identifier (ID) of the root, OU, or account from which you want to detach the policy. You can get the ID from the  list-roots ,  list-organizational-units-for-parent , or  list-accounts operations.

   

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

**To detach a policy from an OU**

The following example shows how to detach a policy from an OU.

Command::

  aws organizations detach-policy --target-id ou-examplerootid111-exampleouid111 --policy-id p-examplepolicyid111

======
Output
======

None