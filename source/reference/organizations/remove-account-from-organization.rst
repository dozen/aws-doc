[ :ref:`aws <cli:aws>` . :ref:`organizations <cli:aws organizations>` ]

.. _cli:aws organizations remove-account-from-organization:


********************************
remove-account-from-organization
********************************



===========
Description
===========



Removes the specified account from the organization.

 

The removed account becomes a stand-alone account that is not a member of any organization. It is no longer subject to any policies and is responsible for its own bill payments. The organization's master account is no longer charged for any expenses accrued by the member account after it is removed from the organization.

 

This operation can be called only from the organization's master account. Member accounts can remove themselves with  leave-organization instead.

 

.. warning::

   

   
  * You can remove only accounts that were created outside your organization and invited to join. If you created the account using the AWS Organizations console, the Organizations API, or the Organizations CLI commands, then you cannot remove the account. 
   
  * You can remove a member account only after you enable IAM user access to billing in the member account. For more information, see `Activating Access to the Billing and Cost Management Console <http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/grantaccess.html#ControllingAccessWebsite-Activate>`_ in the *AWS Billing and Cost Management User Guide* . 
   

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/organizations-2016-11-28/RemoveAccountFromOrganization>`_


========
Synopsis
========

::

    remove-account-from-organization
  --account-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--account-id`` (string)


  The unique identifier (ID) of the member account that you want to remove from the organization.

   

  The `regex pattern <http://wikipedia.org/wiki/regex>`_ for an account ID string requires exactly 12 digits.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To remove a member account from the organization as a user in the master account**

The following example shows how to remove member account 333333333333 from an organization.  

Command::

  aws organizations remove-account --account-id 333333333333

======
Output
======

None