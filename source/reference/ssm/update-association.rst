[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm update-association:


******************
update-association
******************



===========
Description
===========



Updates an association. You can only update the document version, schedule, parameters, and Amazon S3 output of an association.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/UpdateAssociation>`_


========
Synopsis
========

::

    update-association
  --association-id <value>
  [--parameters <value>]
  [--document-version <value>]
  [--schedule-expression <value>]
  [--output-location <value>]
  [--name <value>]
  [--targets <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--association-id`` (string)


  The ID of the association you want to update. 

  

``--parameters`` (map)


  The parameters you want to update for the association. If you create a parameter using Parameter Store, you can reference the parameter using {{ssm:parameter-name}}

  



Shorthand Syntax::

    KeyName1=string,string,KeyName2=string,string




JSON Syntax::

  {"string": ["string", ...]
    ...}



``--document-version`` (string)


  The document version you want update for the association. 

  

``--schedule-expression`` (string)


  The cron expression used to schedule the association that you want to update.

  

``--output-location`` (structure)


  An Amazon S3 bucket where you want to store the results of this request.

  



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



``--name`` (string)


  The name of the association document.

  

``--targets`` (list)


  The targets of the association.

  



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



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To update a document association**

This example updates an association with a new document version.

Command::

  aws ssm update-association --association-id "4cc73e42-d5ae-4879-84f8-57e09c0efcd0" --document-version "\$LATEST"

Output::

  {
    "AssociationDescription": {
        "LastSuccessfulExecutionDate": 1487906247.0,
        "Name": "AWS-UpdateSSMAgent",
        "LastExecutionDate": 1487906247.0,
        "Overview": {
            "Status": "Success",
            "AssociationStatusAggregatedCount": {
                "Success": 1
            }
        },
        "AssociationId": "4cc73e42-d5ae-4879-84f8-57e09c0efcd0",
        "DocumentVersion": "$LATEST",
        "LastUpdateAssociationDate": 1487906288.447,
        "Date": 1487906246.999,
        "Targets": [
            {
                "Values": [
                    "i-0cb2b964d3e14fd9f"
                ],
                "Key": "instanceids"
            }
        ]
    }
  }


======
Output
======

AssociationDescription -> (structure)

  

  The description of the association that was updated.

  

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

    

    

  

