[ :ref:`aws <cli:aws>` . :ref:`appstream <cli:aws appstream>` ]

.. _cli:aws appstream update-directory-config:


***********************
update-directory-config
***********************



===========
Description
===========



Updates the directory configuration with the given parameters.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/appstream-2016-12-01/UpdateDirectoryConfig>`_


========
Synopsis
========

::

    update-directory-config
  --directory-name <value>
  [--organizational-unit-distinguished-names <value>]
  [--service-account-credentials <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--directory-name`` (string)


  The name of the existing directory configuration to be updated.

  

``--organizational-unit-distinguished-names`` (list)


  The list of the distinguished names of organizational units to place computer accounts in.

  



Syntax::

  "string" "string" ...



``--service-account-credentials`` (structure)


  The *AccountName* and *AccountPassword* values for the service account, which are used by the streaming instance to connect to the directory

  



Shorthand Syntax::

    AccountName=string,AccountPassword=string




JSON Syntax::

  {
    "AccountName": "string",
    "AccountPassword": "string"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

DirectoryConfig -> (structure)

  

  The updated directory configuration details.

  

  DirectoryName -> (string)

    

    The fully qualified name of the directory, such as corp.example.com

    

    

  OrganizationalUnitDistinguishedNames -> (list)

    

    The list of the distinguished names of organizational units in which to place computer accounts.

    

    (string)

      

      

    

  ServiceAccountCredentials -> (structure)

    

    The *AccountName* and *AccountPassword* of the service account, to be used by the streaming instance to connect to the directory.

    

    AccountName -> (string)

      

      The user name of an account in the directory that is used by AppStream 2.0 streaming instances to connect to the directory. This account must have the following privileges: create computer objects, join computers to the domain, change/reset the password on descendant computer objects for the organizational units specified.

      

      

    AccountPassword -> (string)

      

      The password for the user account for directory actions.

      

      

    

  CreatedTime -> (timestamp)

    

    The time stamp when the directory configuration was created within AppStream 2.0.

    

    

  

