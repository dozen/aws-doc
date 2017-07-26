[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm update-association-status:


*************************
update-association-status
*************************



===========
Description
===========



Updates the status of the SSM document associated with the specified instance.



========
Synopsis
========

::

    update-association-status
  --name <value>
  --instance-id <value>
  --association-status <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--name`` (string)


  The name of the SSM document.

  

``--instance-id`` (string)


  The ID of the instance.

  

``--association-status`` (structure)


  The association status.

  



Shorthand Syntax::

    Date=timestamp,Name=string,Message=string,AdditionalInfo=string




JSON Syntax::

  {
    "Date": timestamp,
    "Name": "Pending"|"Success"|"Failed",
    "Message": "string",
    "AdditionalInfo": "string"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To update the association status**

This example updates the association status of the association between instance ``i-1a2b3c4d`` and configuration document ``My_Config_1``.

Command::

  aws ssm update-association-status --name My_Config_1 --instance-id i-1a2b3c4d --association-status Date=1424421071.939,Name=Pending,Message=temp_status_change,AdditionalInfo=Additional-Config-Needed


Output::

 {
    "AssociationDescription": {
        "InstanceId": "i-1a2b3c4d", 
        "Date": 1424421071.939, 
        "Name": "My_Config_1", 
        "Status": {
            "Date": 1424421071.0, 
            "AdditionalInfo": "Additional-Config-Needed", 
            "Message": "temp_status_change", 
            "Name": "Pending"
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

        

        

      

    

  

