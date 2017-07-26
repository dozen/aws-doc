[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm list-associations:


*****************
list-associations
*****************



===========
Description
===========



Lists the associations for the specified Systems Manager document or instance.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/ListAssociations>`_


``list-associations`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Associations``


========
Synopsis
========

::

    list-associations
  [--association-filter-list <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--association-filter-list`` (list)


  One or more filters. Use a filter to return a more specific list of results.

  



Shorthand Syntax::

    key=string,value=string ...




JSON Syntax::

  [
    {
      "key": "InstanceId"|"Name"|"AssociationId"|"AssociationStatusName"|"LastExecutedBefore"|"LastExecutedAfter",
      "value": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``next-token`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``next-token`` is provided in the command's output. To resume pagination, provide the ``next-token`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``next-token`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To list your associations for a specific instance**

This example lists all the associations for an instance.

Command::

  aws ssm list-associations --association-filter-list "key=InstanceId,value=i-0000293ffd8c57862"

Output::

  {
    "Associations": [
        {
            "InstanceId": "i-0000293ffd8c57862",
            "Overview": {
                "Status": "Pending",
                "DetailedStatus": "Associated",
                "AssociationStatusAggregatedCount": {
                    "Pending": 1
                }
            },
            "AssociationId": "d8617c07-2079-4c18-9847-1655fc2698b0",
            "Name": "AWS-UpdateSSMAgent",
            "Targets": [
                {
                    "Values": [
                        "i-0000293ffd8c57862"
                    ],
                    "Key": "InstanceIds"
                }
            ]
        }
    ]
  }

**To list your associations for a specific document**

This example lists all associations for the a document.

Command::

  aws ssm list-associations --association-filter-list "key=Name,value=AWS-UpdateSSMAgent"

Output::

  {
    "Associations": [
        {
            "InstanceId": "i-0000293ffd8c57862",
            "Overview": {
                "Status": "Pending",
                "DetailedStatus": "Associated",
                "AssociationStatusAggregatedCount": {
                    "Pending": 1
                }
            },
            "AssociationId": "d8617c07-2079-4c18-9847-1655fc2698b0",
            "Name": "AWS-UpdateSSMAgent",
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
            "Name": "AWS-UpdateSSMAgent",
            "LastExecutionDate": 1487876123.0,
            "InstanceId": "i-0cb2b964d3e14fd9f",
            "Overview": {
                "Status": "Success",
                "AssociationStatusAggregatedCount": {
                    "Success": 1
                }
            },
            "AssociationId": "2ccfbc46-5fe4-4e5c-ba46-70b56cc93f53",
            "Targets": [
                {
                    "Values": [
                        "i-0cb2b964d3e14fd9f"
                    ],
                    "Key": "InstanceIds"
                }
            ]
        }
    ]
  }


======
Output
======

Associations -> (list)

  

  The associations.

  

  (structure)

    

    Describes an association of a Systems Manager document and an instance.

    

    Name -> (string)

      

      The name of the SSM document.

      

      

    InstanceId -> (string)

      

      The ID of the instance.

      

      

    AssociationId -> (string)

      

      The ID created by the system when you create an association. An association is a binding between a document and a set of targets with a schedule.

      

      

    DocumentVersion -> (string)

      

      The version of the document used in the association.

      

      

    Targets -> (list)

      

      The instances targeted by the request to create an association. 

      

      (structure)

        

        An array of search criteria that targets instances using a Key,Value combination that you specify. ``Targets`` is required if you don't provide one or more instance IDs in the call.

         

        

        

        Key -> (string)

          

          User-defined criteria for sending commands that target instances that meet the criteria. Key can be tag:Amazon EC2 tagor InstanceIds. For more information about how to send commands that target instances using Key,Value parameters, see `Executing a Command Using Systems Manager Run Command <http://docs.aws.amazon.com/systems-manager/latest/userguide/send-commands-multiple.html>`_ .

          

          

        Values -> (list)

          

          User-defined criteria that maps to Key. For example, if you specified tag:ServerRole, you could specify value:WebServer to execute a command on instances that include Amazon EC2 tags of ServerRole,WebServer. For more information about how to send commands that target instances using Key,Value parameters, see `Executing a Command Using Systems Manager Run Command <http://docs.aws.amazon.com/systems-manager/latest/userguide/send-commands-multiple.html>`_ .

          

          (string)

            

            

          

        

      

    LastExecutionDate -> (timestamp)

      

      The date on which the association was last run.

      

      

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

          

          

        

      

    ScheduleExpression -> (string)

      

      A cron expression that specifies a schedule when the association runs.

      

      

    

  

NextToken -> (string)

  

  The token to use when requesting the next set of items. If there are no additional items to return, the string is empty.

  

  

