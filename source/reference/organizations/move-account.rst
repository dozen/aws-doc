[ :ref:`aws <cli:aws>` . :ref:`organizations <cli:aws organizations>` ]

.. _cli:aws organizations move-account:


************
move-account
************



===========
Description
===========



Moves an account from its current source parent root or OU to the specified destination parent root or OU.

 

This operation can be called only from the organization's master account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/organizations-2016-11-28/MoveAccount>`_


========
Synopsis
========

::

    move-account
  --account-id <value>
  --source-parent-id <value>
  --destination-parent-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--account-id`` (string)


  The unique identifier (ID) of the account that you want to move.

   

  The `regex pattern <http://wikipedia.org/wiki/regex>`_ for an account ID string requires exactly 12 digits.

  

``--source-parent-id`` (string)


  The unique identifier (ID) of the root or organizational unit that you want to move the account from.

   

  The `regex pattern <http://wikipedia.org/wiki/regex>`_ for a parent ID string requires one of the following:

   

   
  * Root: a string that begins with "r-" followed by from 4 to 32 lower-case letters or digits. 
   
  * Organizational unit (OU): a string that begins with "ou-" followed by from 4 to 32 lower-case letters or digits (the ID of the root that the OU is in) followed by a second "-" dash and from 8 to 32 additional lower-case letters or digits. 
   

  

``--destination-parent-id`` (string)


  The unique identifier (ID) of the root or organizational unit that you want to move the account to.

   

  The `regex pattern <http://wikipedia.org/wiki/regex>`_ for a parent ID string requires one of the following:

   

   
  * Root: a string that begins with "r-" followed by from 4 to 32 lower-case letters or digits. 
   
  * Organizational unit (OU): a string that begins with "ou-" followed by from 4 to 32 lower-case letters or digits (the ID of the root that the OU is in) followed by a second "-" dash and from 8 to 32 additional lower-case letters or digits. 
   

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To move an account to a different OU or root**

The following example shows how to move a member account from the root to an OU.  

Command::

  aws organizations move-account --account-id 333333333333 --source-parent-id r-examplerootid111 --destination-parent-id ou-examplerootid111-exampleouid111

======
Output
======

None