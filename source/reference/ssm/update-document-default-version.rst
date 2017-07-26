[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm update-document-default-version:


*******************************
update-document-default-version
*******************************



===========
Description
===========



Set the default version of a document. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/UpdateDocumentDefaultVersion>`_


========
Synopsis
========

::

    update-document-default-version
  --name <value>
  --document-version <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  The name of a custom document that you want to set as the default version.

  

``--document-version`` (string)


  The version of a custom document that you want to set as the default version.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To update the default version of a Document**

This updates the default version of a document. There is no output if the command succeeds.

Command::

  aws ssm update-document-default-version --name "patchWindowsAmi" --document-version "2"


======
Output
======

Description -> (structure)

  

  The description of a custom document that you want to set as the default version.

  

  Name -> (string)

    

    The name of the document.

    

    

  DefaultVersion -> (string)

    

    The default version of the document.

    

    

  

