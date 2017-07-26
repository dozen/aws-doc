[ :ref:`aws <cli:aws>` . :ref:`organizations <cli:aws organizations>` ]

.. _cli:aws organizations update-organizational-unit:


**************************
update-organizational-unit
**************************



===========
Description
===========



Renames the specified organizational unit (OU). The ID and ARN do not change. The child OUs and accounts remain in place, and any attached policies of the OU remain attached. 

 

This operation can be called only from the organization's master account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/organizations-2016-11-28/UpdateOrganizationalUnit>`_


========
Synopsis
========

::

    update-organizational-unit
  --organizational-unit-id <value>
  [--name <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--organizational-unit-id`` (string)


  The unique identifier (ID) of the OU that you want to rename. You can get the ID from the  list-organizational-units-for-parent operation.

   

  The `regex pattern <http://wikipedia.org/wiki/regex>`_ for an organizational unit ID string requires "ou-" followed by from 4 to 32 lower-case letters or digits (the ID of the root that contains the OU) followed by a second "-" dash and from 8 to 32 additional lower-case letters or digits.

  

``--name`` (string)


  The new name that you want to assign to the OU.

   

  The `regex pattern <http://wikipedia.org/wiki/regex>`_ that is used to validate this parameter is a string of any of the characters in the ASCII character range.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To rename an OU**

The following example shows how to rename an OU. 

Command::

  aws organizations update-organizational-unit --organizational-unit-id ou-examplerootid111-exampleouid111 --name AccountingOU
  
The output confirms the new name.

Output::

  {
    "OrganizationalUnit": {
      "Id": "ou-examplerootid111-exampleouid111",
      "Name": "AccountingOU",
      "Arn": "arn:aws:organizations::111111111111:ou/o-exampleorgid/ou-examplerootid111-exampleouid111"
    }
  }

======
Output
======

OrganizationalUnit -> (structure)

  

  A structure that contains the details about the specified OU, including its new name.

  

  Id -> (string)

    

    The unique identifier (ID) associated with this OU.

     

    The `regex pattern <http://wikipedia.org/wiki/regex>`_ for an organizational unit ID string requires "ou-" followed by from 4 to 32 lower-case letters or digits (the ID of the root that contains the OU) followed by a second "-" dash and from 8 to 32 additional lower-case letters or digits.

    

    

  Arn -> (string)

    

    The Amazon Resource Name (ARN) of this OU.

     

    For more information about ARNs in Organizations, see `ARN Formats Supported by Organizations <http://docs.aws.amazon.com/organizations/latest/userguide/orgs_permissions.html#orgs-permissions-arns>`_ in the *AWS Organizations User Guide* .

    

    

  Name -> (string)

    

    The friendly name of this OU.

     

    The `regex pattern <http://wikipedia.org/wiki/regex>`_ that is used to validate this parameter is a string of any of the characters in the ASCII character range.

    

    

  

