[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm describe-instance-information:


*****************************
describe-instance-information
*****************************



===========
Description
===========



Describes one or more of your instances. You can use this to get information about instances like the operating system platform, the SSM Agent version (Linux), status etc. If you specify one or more instance IDs, it returns information for those instances. If you do not specify instance IDs, it returns information for all your instances. If you specify an instance ID that is not valid or an instance that you do not own, you receive an error. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/DescribeInstanceInformation>`_


``describe-instance-information`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``InstanceInformationList``


========
Synopsis
========

::

    describe-instance-information
  [--instance-information-filter-list <value>]
  [--filters <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--instance-information-filter-list`` (list)


  One or more filters. Use a filter to return a more specific list of instances.

  



Shorthand Syntax::

    key=string,valueSet=string,string ...




JSON Syntax::

  [
    {
      "key": "InstanceIds"|"AgentVersion"|"PingStatus"|"PlatformTypes"|"ActivationIds"|"IamRole"|"ResourceType"|"AssociationStatus",
      "valueSet": ["string", ...]
    }
    ...
  ]



``--filters`` (list)


  One or more filters. Use a filter to return a more specific list of instances.

  



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

**To describe instance information**

This example shows details of each of your instances.

Command::

  aws ssm describe-instance-information

Output::

  {
    "InstanceInformationList": [
        {
            "IsLatestVersion": true,
            "LastSuccessfulAssociationExecutionDate": 1487876123.0,
            "ComputerName": "ip-172-31-44-222.us-west-2.compute.internal",
            "PingStatus": "Online",
            "InstanceId": "i-0cb2b964d3e14fd9f",
            "IPAddress": "172.31.44.222",
            "AssociationStatus": "Success",
            "LastAssociationExecutionDate": 1487876123.0,
            "ResourceType": "EC2Instance",
            "AgentVersion": "2.0.672.0",
            "PlatformVersion": "2016.09",
            "AssociationOverview": {
                "InstanceAssociationStatusAggregatedCount": {
                    "Success": 1
                }
            },
            "PlatformName": "Amazon Linux AMI",
            "PlatformType": "Linux",
            "LastPingDateTime": 1487898903.758
        }
    ]
  }

**To describe information about a specific instance**

This example shows details of instance ``i-0cb2b964d3e14fd9f``.

Command::

  aws ssm describe-instance-information --instance-information-filter-list "key=InstanceIds,valueSet=i-0cb2b964d3e14fd9f"


======
Output
======

InstanceInformationList -> (list)

  

  The instance information list.

  

  (structure)

    

    Describes a filter for a specific list of instances. 

    

    InstanceId -> (string)

      

      The instance ID. 

      

      

    PingStatus -> (string)

      

      Connection status of the SSM Agent. 

      

      

    LastPingDateTime -> (timestamp)

      

      The date and time when agent last pinged Systems Manager service. 

      

      

    AgentVersion -> (string)

      

      The version of the SSM Agent running on your Linux instance. 

      

      

    IsLatestVersion -> (boolean)

      

      Indicates whether latest version of the SSM Agent is running on your instance. 

      

      

    PlatformType -> (string)

      

      The operating system platform type. 

      

      

    PlatformName -> (string)

      

      The name of the operating system platform running on your instance. 

      

      

    PlatformVersion -> (string)

      

      The version of the OS platform running on your instance. 

      

      

    ActivationId -> (string)

      

      The activation ID created by Systems Manager when the server or VM was registered.

      

      

    IamRole -> (string)

      

      The Amazon Identity and Access Management (IAM) role assigned to EC2 instances or managed instances. 

      

      

    RegistrationDate -> (timestamp)

      

      The date the server or VM was registered with AWS as a managed instance.

      

      

    ResourceType -> (string)

      

      The type of instance. Instances are either EC2 instances or managed instances. 

      

      

    Name -> (string)

      

      The name of the managed instance.

      

      

    IPAddress -> (string)

      

      The IP address of the managed instance.

      

      

    ComputerName -> (string)

      

      The fully qualified host name of the managed instance.

      

      

    AssociationStatus -> (string)

      

      The status of the association.

      

      

    LastAssociationExecutionDate -> (timestamp)

      

      The date the association was last executed.

      

      

    LastSuccessfulAssociationExecutionDate -> (timestamp)

      

      The last date the association was successfully run.

      

      

    AssociationOverview -> (structure)

      

      Information about the association.

      

      DetailedStatus -> (string)

        

        Detailed status information about the aggregated associations.

        

        

      InstanceAssociationStatusAggregatedCount -> (map)

        

        The number of associations for the instance(s).

        

        key -> (string)

          

          

        value -> (integer)

          

          

        

      

    

  

NextToken -> (string)

  

  The token to use when requesting the next set of items. If there are no additional items to return, the string is empty. 

  

  

