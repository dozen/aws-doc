[ :ref:`aws <cli:aws>` . :ref:`appstream <cli:aws appstream>` ]

.. _cli:aws appstream describe-directory-configs:


**************************
describe-directory-configs
**************************



===========
Description
===========



Returns a list describing the specified directory configurations.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/appstream-2016-12-01/DescribeDirectoryConfigs>`_


========
Synopsis
========

::

    describe-directory-configs
  [--directory-names <value>]
  [--max-results <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--directory-names`` (list)


  A specific list of directory names.

  



Syntax::

  "string" "string" ...



``--max-results`` (integer)


  The size of each page of results.

  

``--next-token`` (string)


  The DescribeDirectoryConfigsResult.NextToken from a previous call to DescribeDirectoryConfigs. If this is the first call, pass null.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

DirectoryConfigs -> (list)

  

  The list of directory configurations.

  

  (structure)

    

    Full directory configuration details, which are used to join domains for the AppStream 2.0 streaming instances.

    

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

      

      

    

  

NextToken -> (string)

  

  If not null, more results are available. To retrieve the next set of items, pass this value for the NextToken parameter in a subsequent call to DescribeDirectoryConfigs.

  

  

