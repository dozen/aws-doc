[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm describe-instance-associations-status:


*************************************
describe-instance-associations-status
*************************************



===========
Description
===========



The status of the associations for the instance(s).



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/DescribeInstanceAssociationsStatus>`_


========
Synopsis
========

::

    describe-instance-associations-status
  --instance-id <value>
  [--max-results <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--instance-id`` (string)


  The instance IDs for which you want association status information.

  

``--max-results`` (integer)


  The maximum number of items to return for this call. The call also returns a token that you can specify in a subsequent call to get the next set of results.

  

``--next-token`` (string)


  The token for the next set of items to return. (You received this token from a previous call.)

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe the status of an instance's associations**

This example shows details of the associations for an instance.

Command::

  aws ssm describe-instance-associations-status --instance-id "i-0000293ffd8c57862"

Output::

  {
    "InstanceAssociationStatusInfos": [
        {
            "Status": "Pending",
            "DetailedStatus": "Associated",
            "Name": "AWS-UpdateSSMAgent",
            "InstanceId": "i-0000293ffd8c57862",
            "AssociationId": "d8617c07-2079-4c18-9847-1655fc2698b0",
            "DocumentVersion": "1"
        }
    ]
  }


======
Output
======

InstanceAssociationStatusInfos -> (list)

  

  Status information about the association.

  

  (structure)

    

    Status information about the instance association.

    

    AssociationId -> (string)

      

      The association ID.

      

      

    Name -> (string)

      

      The name of the association.

      

      

    DocumentVersion -> (string)

      

      The association document verions.

      

      

    InstanceId -> (string)

      

      The instance ID where the association was created.

      

      

    ExecutionDate -> (timestamp)

      

      The date the instance association executed. 

      

      

    Status -> (string)

      

      Status information about the instance association.

      

      

    DetailedStatus -> (string)

      

      Detailed status information about the instance association.

      

      

    ExecutionSummary -> (string)

      

      Summary information about association execution.

      

      

    ErrorCode -> (string)

      

      An error code returned by the request to create the association.

      

      

    OutputUrl -> (structure)

      

      A URL for an Amazon S3 bucket where you want to store the results of this request.

      

      S3OutputUrl -> (structure)

        

        The URL of Amazon S3 bucket where you want to store the results of this request.

        

        OutputUrl -> (string)

          

          A URL for an Amazon S3 bucket where you want to store the results of this request.

          

          

        

      

    

  

NextToken -> (string)

  

  The token to use when requesting the next set of items. If there are no additional items to return, the string is empty.

  

  

