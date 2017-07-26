[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm create-association-batch:


************************
create-association-batch
************************



===========
Description
===========



Associates the specified SSM document with the specified instances.

 

When you associate an SSM document with an instance, the configuration agent on the instance processes the document and configures the instance as specified.

 

If you associate a document with an instance that already has an associated document, the system throws the AssociationAlreadyExists exception.



========
Synopsis
========

::

    create-association-batch
  --entries <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--entries`` (list)


  One or more associations.

  



Shorthand Syntax::

    Name=string,InstanceId=string,Parameters={KeyName1=string,string,KeyName2=string,string} ...




JSON Syntax::

  [
    {
      "Name": "string",
      "InstanceId": "string",
      "Parameters": {"string": ["string", ...]
        ...}
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To create multiple associations**

This example associates the configuration document ``My_Config_1`` with instance ``i-aabb2233``, and associates the configuration document ``My_Config_2`` with instance ``i-cdcd2233``. The output returns a list of successful and unsuccessful operations, if applicable.

Command::

  aws ssm create-association-batch --entries Name=My_Config_1,InstanceId=i-aabb2233 Name=My_Config_2,InstanceId=1-cdcd2233

Output::


 {
    "Successful": [
        {
            "InstanceId": "i-aabb2233", 
            "Date": 1424421071.939, 
            "Name": My_Config_1", 
            "Status": {
                "Date": 1424421071.939, 
                "Message": "Associated with My_Config_1", 
                "Name": "Associated"
            }
        }
    ], 
    "Failed": [
        {
            "Entry": {
                "InstanceId": "i-cdcd2233", 
                "Name": "My_Config_2"
            }, 
            "Message": "Association Already Exists", 
            "Fault": "Client"
        }
    ]
 }

======
Output
======

Successful -> (list)

  

  Information about the associations that succeeded.

  

  (structure)

    

    Describes the parameters for a document.

    

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

          

          

        

      

    

  

Failed -> (list)

  

  Information about the associations that failed.

  

  (structure)

    

    Describes a failed association.

    

    Entry -> (structure)

      

      The association.

      

      Name -> (string)

        The name of the configuration document.

        

      InstanceId -> (string)

        The ID of the instance.

        

      Parameters -> (map)

        A description of the parameters for a document.

        key -> (string)

          

          

        value -> (list)

          

          (string)

            

            

          

        

      

    Message -> (string)

      

      A description of the failure.

      

      

    Fault -> (string)

      

      The source of the failure.

      

      

    

  

