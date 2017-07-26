[ :ref:`aws <cli:aws>` . :ref:`organizations <cli:aws organizations>` ]

.. _cli:aws organizations delete-organization:


*******************
delete-organization
*******************



===========
Description
===========



Deletes the organization. You can delete an organization only by using credentials from the master account. The organization must be empty of member accounts, OUs, and policies.

 

.. warning::

   

  If you create any accounts using Organizations operations or the Organizations console, you can't remove those accounts from the organization, which means that you can't delete the organization.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/organizations-2016-11-28/DeleteOrganization>`_


========
Synopsis
========

::

    delete-organization
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

**To delete an organization**

The following example shows how to delete an organization. To perform this operation, you must be an admin of the master account in the organization. The example assumes that you previously removed all the member accounts, OUs, and policies from the organization.

Command::

  aws organizations delete-organization

======
Output
======

None