[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm describe-document:


*****************
describe-document
*****************



===========
Description
===========



Describes the specified SSM document.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/DescribeDocument>`_


========
Synopsis
========

::

    describe-document
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


  The document version for which you want information. Can be a specific version or the default version.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe a configuration document**

This example returns the content of a document.

Command::

  aws ssm describe-document --name "RunShellScript"
  
Output::

  {
    "Document": {
        "Status": "Active",
        "Hash": "95cf32aa8c4c4e6f0eb81c4d0cc9a81aa5d209c2c67c703bdea7a233b5596eba",
        "Name": "RunShellScript",
        "Parameters": [
            {
                "Type": "StringList",
                "Name": "commands",
                "Description": "(Required) Specify a shell script or a command to run."
            }
        ],
        "DocumentType": "Command",
        "PlatformTypes": [
            "Linux"
        ],
        "DocumentVersion": "1",
        "HashType": "Sha256",
        "CreatedDate": 1487871400.888,
        "Owner": "809632081692",
        "SchemaVersion": "2.0",
        "DefaultVersion": "1",
        "LatestVersion": "1",
        "Description": "Run a script"
    }
  }


======
Output
======

Document -> (structure)

  

  Information about the SSM document.

  

  Sha1 -> (string)

    

    The SHA1 hash of the document, which you can use for verification purposes.

    

    

  Hash -> (string)

    

    The Sha256 or Sha1 hash created by the system when the document was created. 

     

    .. note::

       

      Sha1 hashes have been deprecated.

       

    

    

  HashType -> (string)

    

    Sha256 or Sha1.

     

    .. note::

       

      Sha1 hashes have been deprecated.

       

    

    

  Name -> (string)

    

    The name of the SSM document.

    

    

  Owner -> (string)

    

    The AWS user account of the person who created the document.

    

    

  CreatedDate -> (timestamp)

    

    The date when the document was created.

    

    

  Status -> (string)

    

    The status of the SSM document.

    

    

  DocumentVersion -> (string)

    

    The document version.

    

    

  Description -> (string)

    

    A description of the document. 

    

    

  Parameters -> (list)

    

    A description of the parameters for a document.

    

    (structure)

      

      Parameters specified in a System Manager document that execute on the server when the command is run. 

      

      Name -> (string)

        

        The name of the parameter.

        

        

      Type -> (string)

        

        The type of parameter. The type can be either String or StringList.

        

        

      Description -> (string)

        

        A description of what the parameter does, how to use it, the default value, and whether or not the parameter is optional.

        

        

      DefaultValue -> (string)

        

        If specified, the default values for the parameters. Parameters without a default value are required. Parameters with a default value are optional.

        

        

      

    

  PlatformTypes -> (list)

    

    The list of OS platforms compatible with this SSM document. 

    

    (string)

      

      

    

  DocumentType -> (string)

    

    The type of document. 

    

    

  SchemaVersion -> (string)

    

    The schema version.

    

    

  LatestVersion -> (string)

    

    The latest version of the document.

    

    

  DefaultVersion -> (string)

    

    The default version.

    

    

  

