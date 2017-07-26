[ :ref:`aws <cli:aws>` . :ref:`organizations <cli:aws organizations>` ]

.. _cli:aws organizations leave-organization:


******************
leave-organization
******************



===========
Description
===========



Removes a member account from its parent organization. This version of the operation is performed by the account that wants to leave. To remove a member account as a user in the master account, use  remove-account-from-organization instead.

 

This operation can be called only from a member account in the organization.

 

.. warning::

   

   
  * The master account in an organization with all features enabled can set service control policies (SCPs) that can restrict what administrators of member accounts can do, including preventing them from successfully calling ``leave-organization`` and leaving the organization.  
   
  * If you created the account using the AWS Organizations console, the Organizations API, or the Organizations CLI commands, then you cannot remove the account. 
   
  * You can leave an organization only after you enable IAM user access to billing in your account. For more information, see `Activating Access to the Billing and Cost Management Console <http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/grantaccess.html#ControllingAccessWebsite-Activate>`_ in the *AWS Billing and Cost Management User Guide* . 
   

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/organizations-2016-11-28/LeaveOrganization>`_


========
Synopsis
========

::

    leave-organization
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To leave an organization**

The following example shows how to remove your member account from an organization.  

Command::

  aws organizations leave-organization

======
Output
======

None