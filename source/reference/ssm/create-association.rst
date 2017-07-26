[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm create-association:


******************
create-association
******************



===========
Description
===========



Associates the specified SSM document with the specified instance.

 

When you associate an SSM document with an instance, the configuration agent on the instance processes the document and configures the instance as specified.

 

If you associate a document with an instance that already has an associated document, the system throws the AssociationAlreadyExists exception.



========
Synopsis
========

::

    create-association
  --name <value>
  --instance-id <value>
  [--parameters <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--name`` (string)


  The name of the SSM document.

  

``--instance-id`` (string)


  The Windows Server instance ID.

  

``--parameters`` (map)
The parameters for the documents runtime configuration.



Shorthand Syntax::

    KeyName1=string,string,KeyName2=string,string




JSON Syntax::

  {"string": ["string", ...]
    ...}



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To associate a configuration document**

This example associates configuration document ``My_Config_File`` with instance ``i-1a2b3c4d``.

Command::

  aws ssm create-association --instance-id i-1a2b3c4d --name "My_Config_File"

Output::

   {
     "AssociationDescription": {
         "InstanceId": "i-1a2b3c4d", 
         "Date": 1424354424.842, 
         "Name": "My_Config_File", 
         "Status": {
             "Date": 1424354424.842, 
             "Message": "Associated with My_Config_File", 
             "Name": "Associated"
            }
        }
    }



======
Output
======

AssociationDescription -> (structure)

  

  Information about the association.

  

  Name -> (string)

    

    The name of the SSM document.

    

    

  InstanceId -> (string)

    

    The ID of the instance.

    

    

  Date -> (timestamp)

    

    The date when the association was made.

    

    

  Status -> (structure)

    

    The association status.

    

    Date -> (timestamp)

      

      The date when the status changed.

      

      

    Name -> (string)

      

      The status.

      

      

    Message -> (string)

      

      The reason for the status.

      

      

    AdditionalInfo -> (string)

      

      A user-defined string.

      

      

    

  Parameters -> (map)

    A description of the parameters for a document.

    key -> (string)

      

      

    value -> (list)

      

      (string)

        

        

      

    

  

