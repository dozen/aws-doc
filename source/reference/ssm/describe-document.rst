[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm describe-document:


*****************
describe-document
*****************



===========
Description
===========



Describes the specified SSM document.



========
Synopsis
========

::

    describe-document
  --name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--name`` (string)


  The name of the SSM document.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To describe a configuration document**

This example returns information about a document called ``My_Config_Doc``.

Command::

  aws ssm describe-document --name "My_Config_Doc"
  
Output::

   {
    "Document": {
        "Status": "Active", 
        "Sha1": "715919de171exampleb3d803025817856844a5f3", 
        "Name": "My_Config_Doc", 
        "CreatedDate": 1424351175.521
    }
   }




======
Output
======

Document -> (structure)

  

  Information about the SSM document.

  

  Sha1 -> (string)

    

    The SHA1 hash of the document, which you can use for verification purposes.

    

    

  Name -> (string)

    

    The name of the SSM document.

    

    

  CreatedDate -> (timestamp)

    The date when the SSM document was created.

    

  Status -> (string)

    

    The status of the SSM document.

    

    

  Description -> (string)

    A description of the document.

    

  Parameters -> (list)

    

    A description of the parameters for a document.

    

    (structure)

      

      Name -> (string)

        

        The name of the parameter.

        

        

      Type -> (string)

        

        The type of parameter. The type can be either “String” or “StringList”.

        

        

      Description -> (string)

        

        A description of what the parameter does, how to use it, the default value, and whether or not the parameter is optional.

        

        

      DefaultValue -> (string)

        

        If specified, the default values for the parameters. Parameters without a default value are required. Parameters with a default value are optional.

        

        

      

    

  PlatformTypes -> (list)

    The list of OS platforms compatible with this SSM document.

    (string)

      

      

    

  

