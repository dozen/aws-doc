[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm get-document:


************
get-document
************



===========
Description
===========



Gets the contents of the specified SSM document.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/GetDocument>`_


========
Synopsis
========

::

    get-document
  --name <value>
  [--document-version <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  The name of the SSM document.

  

``--document-version`` (string)


  The document version for which you want information.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To get the contents of a document**

This example returns the content of a document.

Command::

  aws ssm get-document --name "RunShellScript"

Output::

  {
    "Content": "{\n   \"schemaVersion\":\"2.0\",\n   \"description\":\"Run a script\",\n   \"parameters\":{\n      \"commands\":{\n         \"type\":\"StringList\",\n         \"description\":\"(Required) Specify a shell script or a command to run.\",\n         \"minItems\":1,\n         \"displayType\":\"textarea\"\n      }\n   },\n   \"mainSteps\":[\n      {\n         \"action\":\"aws:runShellScript\",\n         \"name\":\"runShellScript\",\n         \"inputs\":{\n            \"commands\":\"{{ commands }}\"\n         }\n      },\n      {\n         \"action\":\"aws:runPowerShellScript\",\n         \"name\":\"runPowerShellScript\",\n         \"inputs\":{\n            \"commands\":\"{{ commands }}\"\n         }\n      }\n   ]\n}\n",
    "Name": "RunShellScript.json",
    "DocumentVersion": "1",
    "DocumentType": "Command"
  }


======
Output
======

Name -> (string)

  

  The name of the SSM document.

  

  

DocumentVersion -> (string)

  

  The document version.

  

  

Content -> (string)

  

  The contents of the SSM document.

  

  

DocumentType -> (string)

  

  The document type.

  

  

