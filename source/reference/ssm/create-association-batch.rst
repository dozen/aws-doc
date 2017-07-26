[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm create-association-batch:


************************
create-association-batch
************************



===========
Description
===========



Associates the specified Systems Manager document with the specified instances or targets.

 

When you associate a document with one or more instances using instance IDs or tags, the SSM Agent running on the instance processes the document and configures the instance as specified.

 

If you associate a document with an instance that already has an associated document, the system throws the AssociationAlreadyExists exception.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/CreateAssociationBatch>`_


========
Synopsis
========

::

    create-association-batch
  --entries <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--entries`` (list)


  One or more associations.

  



JSON Syntax::

  [
    {
      "Name": "string",
      "InstanceId": "string",
      "Parameters": {"string": ["string", ...]
        ...},
      "DocumentVersion": "string",
      "Targets": [
        {
          "Key": "string",
          "Values": ["string", ...]
        }
        ...
      ],
      "ScheduleExpression": "string",
      "OutputLocation": {
        "S3Location": {
          "OutputS3Region": "string",
          "OutputS3BucketName": "string",
          "OutputS3KeyPrefix": "string"
        }
      }
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

**To create multiple associations**

This example associates a configuration document with multiple instances. The output returns a list of successful and failed operations, if applicable.

Command::

  aws ssm create-association-batch --entries "Name=AWS-UpdateSSMAgent,InstanceId=i-0cb2b964d3e14fd9f" "Name=AWS-UpdateSSMAgent,InstanceId=i-0000293ffd8c57862"

Output::

  {
    "Successful": [
        {
            "Status": {
                "Date": 1487876122.564,
                "Message": "Associated with AWS-UpdateSSMAgent",
                "Name": "Associated"
            },
            "Name": "AWS-UpdateSSMAgent",
            "InstanceId": "i-0000293ffd8c57862",
            "Overview": {
                "Status": "Pending",
                "DetailedStatus": "Creating"
            },
            "AssociationId": "d8617c07-2079-4c18-9847-1655fc2698b0",
            "DocumentVersion": "$DEFAULT",
            "LastUpdateAssociationDate": 1487876122.564,
            "Date": 1487876122.564,
            "Targets": [
                {
                    "Values": [
                        "i-0000293ffd8c57862"
                    ],
                    "Key": "InstanceIds"
                }
            ]
        },
        {
            "Status": {
                "Date": 1487876122.595,
                "Message": "Associated with AWS-UpdateSSMAgent",
                "Name": "Associated"
            },
            "Name": "AWS-UpdateSSMAgent",
            "InstanceId": "i-0cb2b964d3e14fd9f",
            "Overview": {
                "Status": "Pending",
                "DetailedStatus": "Creating"
            },
            "AssociationId": "2ccfbc46-5fe4-4e5c-ba46-70b56cc93f53",
            "DocumentVersion": "$DEFAULT",
            "LastUpdateAssociationDate": 1487876122.595,
            "Date": 1487876122.595,
            "Targets": [
                {
                    "Values": [
                        "i-0cb2b964d3e14fd9f"
                    ],
                    "Key": "InstanceIds"
                }
            ]
        }
    ],
    "Failed": []
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

        

        An array of search criteria that targets instances using a Key,Value combination that you specify. ``Targets`` is required if you don't provide one or more instance IDs in the call.

         

        

        

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

            

            

          

        

      DocumentVersion -> (string)

        

        The document version.

        

        

      Targets -> (list)

        

        The instances targeted by the request.

        

        (structure)

          

          An array of search criteria that targets instances using a Key,Value combination that you specify. ``Targets`` is required if you don't provide one or more instance IDs in the call.

           

          

          

          Key -> (string)

            

            User-defined criteria for sending commands that target instances that meet the criteria. Key can be tag:Amazon EC2 tagor InstanceIds. For more information about how to send commands that target instances using Key,Value parameters, see `Executing a Command Using Systems Manager Run Command <http://docs.aws.amazon.com/systems-manager/latest/userguide/send-commands-multiple.html>`_ .

            

            

          Values -> (list)

            

            User-defined criteria that maps to Key. For example, if you specified tag:ServerRole, you could specify value:WebServer to execute a command on instances that include Amazon EC2 tags of ServerRole,WebServer. For more information about how to send commands that target instances using Key,Value parameters, see `Executing a Command Using Systems Manager Run Command <http://docs.aws.amazon.com/systems-manager/latest/userguide/send-commands-multiple.html>`_ .

            

            (string)

              

              

            

          

        

      ScheduleExpression -> (string)

        

        A cron expression that specifies a schedule when the association runs.

        

        

      OutputLocation -> (structure)

        

        An Amazon S3 bucket where you want to store the results of this request.

        

        S3Location -> (structure)

          

          An Amazon S3 bucket where you want to store the results of this request.

          

          OutputS3Region -> (string)

            

            (Deprecated) You can no longer specify this parameter. The system ignores it. Instead, Systems Manager automatically determines the Amazon S3 bucket region.

            

            

          OutputS3BucketName -> (string)

            

            The name of the Amazon S3 bucket.

            

            

          OutputS3KeyPrefix -> (string)

            

            The Amazon S3 bucket subfolder.

            

            

          

        

      

    Message -> (string)

      

      A description of the failure.

      

      

    Fault -> (string)

      

      The source of the failure.

      

      

    

  

