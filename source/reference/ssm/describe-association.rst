[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm describe-association:


********************
describe-association
********************



===========
Description
===========



Describes the associations for the specified SSM document or instance.



========
Synopsis
========

::

    describe-association
  --name <value>
  --instance-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--name`` (string)


  The name of the SSM document.

  

``--instance-id`` (string)


  The Windows Server instance ID.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To describe an association**

This example describes the association between instance ``i-1a2b3c4d`` and ``My_Config_File``.

Command::

  aws ssm describe-association --instance-id i-1a2b3c4d --name "My_Config_File"

Output::

 {
    "AssociationDescription": {
        "InstanceId": "i-1a2b3c4d", 
        "Date": 1424419009.036, 
        "Name": "My_Config_File", 
        "Status": {
            "Date": 1424419196.804, 
            "AdditionalInfo": "{agent=EC2Config,ver=3.0.54,osver=6.3.9600,os=Windows Server 2012 R2 Standard,lang=en-US}", 
            "Message": "RunId=0198dadc-aaaa-4150-875f-exampleba3d, status:InProgress, code:0, message:RuntimeStatusCounts=[PassedAndReboot=1], RuntimeStatus=[aws:domainJoin={PassedAndReboot,Domain join Succeeded to domain: test.ssm.com}]", 
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

        

        

      

    

  

