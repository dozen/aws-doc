[ :ref:`aws <cli:aws>` . :ref:`organizations <cli:aws organizations>` ]

.. _cli:aws organizations delete-organizational-unit:


**************************
delete-organizational-unit
**************************



===========
Description
===========



Deletes an organizational unit from a root or another OU. You must first remove all accounts and child OUs from the OU that you want to delete.

 

This operation can be called only from the organization's master account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/organizations-2016-11-28/DeleteOrganizationalUnit>`_


========
Synopsis
========

::

    delete-organizational-unit
  --organizational-unit-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--organizational-unit-id`` (string)


  The unique identifier (ID) of the organizational unit that you want to delete. You can get the ID from the  list-organizational-units-for-parent operation.

   

  The `regex pattern <http://wikipedia.org/wiki/regex>`_ for an organizational unit ID string requires "ou-" followed by from 4 to 32 lower-case letters or digits (the ID of the root that contains the OU) followed by a second "-" dash and from 8 to 32 additional lower-case letters or digits.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To delete an OU**

The following example shows how to delete an OU. The example assumes that you previously removed all accounts and other OUs from the OU.

Command::

  aws organizations delete-organizational-unit --organizational-unit-id ou-examplerootid111-exampleouid111

======
Output
======

None