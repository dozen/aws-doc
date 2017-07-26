[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm update-document:


***************
update-document
***************



===========
Description
===========



The document you want to update.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/UpdateDocument>`_


========
Synopsis
========

::

    update-document
  --content <value>
  --name <value>
  [--document-version <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--content`` (string)


  The content in a document that you want to update.

  

``--name`` (string)


  The name of the document that you want to update.

  

``--document-version`` (string)


  The version of the document that you want to update.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create a new version of a document**

This creates a new version of a document. The document must be in JSON format. Note that ``file://`` must be referenced followed by the path of the content file.

Command::

  aws ssm update-document --name "RunShellScript" --content "file://RunShellScript.json" --document-version "\$LATEST"
  
Output::

  {
    "DocumentDescription": {
        "Status": "Updating",
        "Hash": "f775e5df4904c6fa46686c4722fae9de1950dace25cd9608ff8d622046b68d9b",
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
        "DocumentVersion": "2",
        "HashType": "Sha256",
        "CreatedDate": 1487899655.152,
        "Owner": "809632081692",
        "SchemaVersion": "2.0",
        "DefaultVersion": "1",
        "LatestVersion": "2",
        "Description": "Run an updated script"
    }
  }


======
Output
======

DocumentDescription -> (structure)

  

  A description of the document that was updated.

  

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

    

    

  

