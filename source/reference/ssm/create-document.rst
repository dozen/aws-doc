[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm create-document:


***************
create-document
***************



===========
Description
===========



Creates an SSM document.

 

After you create an SSM document, you can use  create-association to associate it with one or more running instances.



========
Synopsis
========

::

    create-document
  --content <value>
  --name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--content`` (string)


  A valid JSON string. For more information about the contents of this string, see `SSM Document`_ .

  

``--name`` (string)


  A name for the SSM document.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To create a configuration document**

This example creates a configuration document called ``My_Document`` in your account. The document must be in JSON format. For more information about writing a configuration document, see `Configuration Document`_ in the *SSM API Reference*.

.. _`Configuration Document`: http://docs.aws.amazon.com/ssm/latest/APIReference/aws-ssm-document.html

Command::

  aws ssm create-document --content file://myconfigfile.json --name "My_Config_Document"

Output::

 {
    "DocumentDescription": {
        "Status": "Creating", 
        "Sha1": "715919de1715exampled803025817856844a5f3", 
        "Name": "My_Config_Document", 
        "CreatedDate": 1424351175.521
    }
 }




======
Output
======

DocumentDescription -> (structure)

  

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

      

      

    

  



.. _SSM Document: http://docs.aws.amazon.com/ssm/latest/APIReference/aws-ssm-document.html
