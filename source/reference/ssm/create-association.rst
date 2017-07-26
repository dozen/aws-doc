[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm create-association:


******************
create-association
******************



===========
Description
===========



Associates the specified Systems Manager document with the specified instances or targets.

 

When you associate a document with one or more instances using instance IDs or tags, the SSM Agent running on the instance processes the document and configures the instance as specified.

 

If you associate a document with an instance that already has an associated document, the system throws the AssociationAlreadyExists exception.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/CreateAssociation>`_


========
Synopsis
========

::

    create-association
  --name <value>
  [--document-version <value>]
  [--instance-id <value>]
  [--parameters <value>]
  [--targets <value>]
  [--schedule-expression <value>]
  [--output-location <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  The name of the Systems Manager document.

  

``--document-version`` (string)


  The document version you want to associate with the target(s). Can be a specific version or the default version.

  

``--instance-id`` (string)


  The instance ID.

  

``--parameters`` (map)


  The parameters for the documents runtime configuration. 

  



Shorthand Syntax::

    KeyName1=string,string,KeyName2=string,string




JSON Syntax::

  {"string": ["string", ...]
    ...}



``--targets`` (list)


  The targets (either instances or tags) for the association.

  



Shorthand Syntax::

    Key=string,Values=string,string ...




JSON Syntax::

  [
    {
      "Key": "string",
      "Values": ["string", ...]
    }
    ...
  ]



``--schedule-expression`` (string)


  A cron expression when the association will be applied to the target(s).

  

``--output-location`` (structure)


  An Amazon S3 bucket where you want to store the output details of the request.

  



Shorthand Syntax::

    S3Location={OutputS3Region=string,OutputS3BucketName=string,OutputS3KeyPrefix=string}




JSON Syntax::

  {
    "S3Location": {
      "OutputS3Region": "string",
      "OutputS3BucketName": "string",
      "OutputS3KeyPrefix": "string"
    }
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To associate a document using instance IDs**

This example associates a configuration document with an instance, using instance IDs.

Command::

  aws ssm create-association --instance-id "i-0cb2b964d3e14fd9f" --name "AWS-UpdateSSMAgent"

Output::

  {
    "AssociationDescription": {
        "Status": {
            "Date": 1487875500.33,
            "Message": "Associated with AWS-UpdateSSMAgent",
            "Name": "Associated"
        },
        "Name": "AWS-UpdateSSMAgent",
        "InstanceId": "i-0cb2b964d3e14fd9f",
        "Overview": {
            "Status": "Pending",
            "DetailedStatus": "Creating"
        },
        "AssociationId": "b7c3266e-a544-44db-877e-b20d3a108189",
        "DocumentVersion": "$DEFAULT",
        "LastUpdateAssociationDate": 1487875500.33,
        "Date": 1487875500.33,
        "Targets": [
            {
                "Values": [
                    "i-0cb2b964d3e14fd9f"
                ],
                "Key": "InstanceIds"
            }
        ]
    }
  }

**To associate a document using targets**

This example associates a configuration document with an instance, using targets.

Command::

  aws ssm create-association --name "AWS-UpdateSSMAgent" --targets "Key=instanceids,Values=i-0cb2b964d3e14fd9f"
  

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

    

    

  LastUpdateAssociationDate -> (timestamp)

    

    The date when the association was last updated.

    

    

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

      

      

    

  Overview -> (structure)

    

    Information about the association.

    

    Status -> (string)

      

      The status of the association. Status can be: Pending, Success, or Failed.

      

      

    DetailedStatus -> (string)

      

      A detailed status of the association.

      

      

    AssociationStatusAggregatedCount -> (map)

      

      Returns the number of targets for the association status. For example, if you created an association with two instances, and one of them was successful, this would return the count of instances by status.

      

      key -> (string)

        

        

      value -> (integer)

        

        

      

    

  DocumentVersion -> (string)

    

    The document version.

    

    

  Parameters -> (map)

    

    A description of the parameters for a document. 

    

    key -> (string)

      

      

    value -> (list)

      

      (string)

        

        

      

    

  AssociationId -> (string)

    

    The association ID.

    

    

  Targets -> (list)

    

    The instances targeted by the request. 

    

    (structure)

      

      An array of search criteria that targets instances using a Key,Value combination that you specify. ``targets`` is required if you don't provide one or more instance IDs in the call.

       

      

      

      Key -> (string)

        

        User-defined criteria for sending commands that target instances that meet the criteria. Key can be tag:Amazon EC2 tagor InstanceIds. For more information about how to send commands that target instances using Key,Value parameters, see `Executing a Command Using Systems Manager Run Command <http://docs.aws.amazon.com/systems-manager/latest/userguide/send-commands-multiple.html>`_ .

        

        

      Values -> (list)

        

        User-defined criteria that maps to Key. For example, if you specified tag:ServerRole, you could specify value:WebServer to execute a command on instances that include Amazon EC2 tags of ServerRole,WebServer. For more information about how to send commands that target instances using Key,Value parameters, see `Executing a Command Using Systems Manager Run Command <http://docs.aws.amazon.com/systems-manager/latest/userguide/send-commands-multiple.html>`_ .

        

        (string)

          

          

        

      

    

  ScheduleExpression -> (string)

    

    A cron expression that specifies a schedule when the association runs.

    

    

  OutputLocation -> (structure)

    

    An Amazon S3 bucket where you want to store the output details of the request.

    

    S3Location -> (structure)

      

      An Amazon S3 bucket where you want to store the results of this request.

      

      OutputS3Region -> (string)

        

        (Deprecated) You can no longer specify this parameter. The system ignores it. Instead, Systems Manager automatically determines the Amazon S3 bucket region.

        

        

      OutputS3BucketName -> (string)

        

        The name of the Amazon S3 bucket.

        

        

      OutputS3KeyPrefix -> (string)

        

        The Amazon S3 bucket subfolder.

        

        

      

    

  LastExecutionDate -> (timestamp)

    

    The date on which the association was last run.

    

    

  LastSuccessfulExecutionDate -> (timestamp)

    

    The last date on which the association was successfully run.

    

    

  

