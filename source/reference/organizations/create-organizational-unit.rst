[ :ref:`aws <cli:aws>` . :ref:`organizations <cli:aws organizations>` ]

.. _cli:aws organizations create-organizational-unit:


**************************
create-organizational-unit
**************************



===========
Description
===========



Creates an organizational unit (OU) within a root or parent OU. An OU is a container for accounts that enables you to organize your accounts to apply policies according to your business requirements. The number of levels deep that you can nest OUs is dependent upon the policy types enabled for that root. For service control policies, the limit is five. 

 

For more information about OUs, see `Managing Organizational Units <http://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_ous.html>`_ in the *AWS Organizations User Guide* .

 

This operation can be called only from the organization's master account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/organizations-2016-11-28/CreateOrganizationalUnit>`_


========
Synopsis
========

::

    create-organizational-unit
  --parent-id <value>
  --name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--parent-id`` (string)


  The unique identifier (ID) of the parent root or OU in which you want to create the new OU.

   

  The `regex pattern <http://wikipedia.org/wiki/regex>`_ for a parent ID string requires one of the following:

   

   
  * Root: a string that begins with "r-" followed by from 4 to 32 lower-case letters or digits. 
   
  * Organizational unit (OU): a string that begins with "ou-" followed by from 4 to 32 lower-case letters or digits (the ID of the root that the OU is in) followed by a second "-" dash and from 8 to 32 additional lower-case letters or digits. 
   

  

``--name`` (string)


  The friendly name to assign to the new OU.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create an organizational unit**

The following example shows how to create an OU that is named AccountingOU.

Command::

  aws organizations create-organizational-unit --parent-id r-examplerootid111 --name "AccountingOU"

The output includes an OrganizationalUnit structure that contains details about the new OU.

Output::

  {
    "OrganizationalUnit": {
      "Id": "ou-examplerootid111-exampleouid111",
      "Arn": "arn:aws:organizations::111111111111:ou/o-exampleorgid/ou-examplerootid111-exampleouid111",
      "Name": "AccountingOU"
    }
  }

======
Output
======

OrganizationalUnit -> (structure)

  

  A structure that contains details about the newly created OU.

  

  Id -> (string)

    

    The unique identifier (ID) associated with this OU.

     

    The `regex pattern <http://wikipedia.org/wiki/regex>`_ for an organizational unit ID string requires "ou-" followed by from 4 to 32 lower-case letters or digits (the ID of the root that contains the OU) followed by a second "-" dash and from 8 to 32 additional lower-case letters or digits.

    

    

  Arn -> (string)

    

    The Amazon Resource Name (ARN) of this OU.

     

    For more information about ARNs in Organizations, see `ARN Formats Supported by Organizations <http://docs.aws.amazon.com/organizations/latest/userguide/orgs_permissions.html#orgs-permissions-arns>`_ in the *AWS Organizations User Guide* .

    

    

  Name -> (string)

    

    The friendly name of this OU.

     

    The `regex pattern <http://wikipedia.org/wiki/regex>`_ that is used to validate this parameter is a string of any of the characters in the ASCII character range.

    

    

  

