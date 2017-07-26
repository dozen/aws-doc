[ :ref:`aws <cli:aws>` . :ref:`clouddirectory <cli:aws clouddirectory>` ]

.. _cli:aws clouddirectory list-directories:


****************
list-directories
****************



===========
Description
===========



Lists directories created within an account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/clouddirectory-2016-05-10/ListDirectories>`_


========
Synopsis
========

::

    list-directories
  [--next-token <value>]
  [--max-results <value>]
  [--state <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--next-token`` (string)


  The pagination token.

  

``--max-results`` (integer)


  The maximum number of results to retrieve.

  

``--state`` (string)


  The state of the directories in the list. Can be either Enabled, Disabled, or Deleted.

  

  Possible values:

  
  *   ``ENABLED``

  
  *   ``DISABLED``

  
  *   ``DELETED``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Directories -> (list)

  

  Lists all directories that are associated with your account in pagination fashion.

  

  (structure)

    

    Directory structure that includes the directory name and directory ARN.

    

    Name -> (string)

      

      The name of the directory.

      

      

    DirectoryArn -> (string)

      

      The Amazon Resource Name (ARN) that is associated with the directory. For more information, see  arns .

      

      

    State -> (string)

      

      The state of the directory. Can be either ``Enabled`` , ``Disabled`` , or ``Deleted`` .

      

      

    CreationDateTime -> (timestamp)

      

      The date and time when the directory was created.

      

      

    

  

NextToken -> (string)

  

  The pagination token.

  

  

