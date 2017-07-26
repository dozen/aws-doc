[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-instance-status:


************************
describe-instance-status
************************



===========
Description
===========



Describes the status of one or more instances. By default, only running instances are described, unless you specifically indicate to return the status of all instances.

 

Instance status includes the following components:

 

 
* **Status checks** - Amazon EC2 performs status checks on running EC2 instances to identify hardware and software issues. For more information, see `Status Checks for Your Instances <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/monitoring-system-instance-status-check.html>`_ and `Troubleshooting Instances with Failed Status Checks <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/TroubleshootingInstances.html>`_ in the *Amazon Elastic Compute Cloud User Guide* . 
 
* **Scheduled events** - Amazon EC2 can schedule events (such as reboot, stop, or terminate) for your instances related to hardware issues, software updates, or system maintenance. For more information, see `Scheduled Events for Your Instances <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/monitoring-instances-status-check_sched.html>`_ in the *Amazon Elastic Compute Cloud User Guide* . 
 
* **Instance state** - You can manage your instances from the moment you launch them through their termination. For more information, see `Instance Lifecycle <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-instance-lifecycle.html>`_ in the *Amazon Elastic Compute Cloud User Guide* . 
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeInstanceStatus>`_


``describe-instance-status`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``InstanceStatuses``


========
Synopsis
========

::

    describe-instance-status
  [--filters <value>]
  [--instance-ids <value>]
  [--dry-run | --no-dry-run]
  [--include-all-instances | --no-include-all-instances]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--filters`` (list)


  One or more filters.

   

   
  * ``availability-zone`` - The Availability Zone of the instance. 
   
  * ``event.code`` - The code for the scheduled event (``instance-reboot`` | ``system-reboot`` | ``system-maintenance`` | ``instance-retirement`` | ``instance-stop`` ). 
   
  * ``event.description`` - A description of the event. 
   
  * ``event.not-after`` - The latest end time for the scheduled event (for example, ``2014-09-15T17:15:20.000Z`` ). 
   
  * ``event.not-before`` - The earliest start time for the scheduled event (for example, ``2014-09-15T17:15:20.000Z`` ). 
   
  * ``instance-state-code`` - The code for the instance state, as a 16-bit unsigned integer. The high byte is an opaque internal value and should be ignored. The low byte is set based on the state represented. The valid values are 0 (pending), 16 (running), 32 (shutting-down), 48 (terminated), 64 (stopping), and 80 (stopped). 
   
  * ``instance-state-name`` - The state of the instance (``pending`` | ``running`` | ``shutting-down`` | ``terminated`` | ``stopping`` | ``stopped`` ). 
   
  * ``instance-status.reachability`` - Filters on instance status where the name is ``reachability`` (``passed`` | ``failed`` | ``initializing`` | ``insufficient-data`` ). 
   
  * ``instance-status.status`` - The status of the instance (``ok`` | ``impaired`` | ``initializing`` | ``insufficient-data`` | ``not-applicable`` ). 
   
  * ``system-status.reachability`` - Filters on system status where the name is ``reachability`` (``passed`` | ``failed`` | ``initializing`` | ``insufficient-data`` ). 
   
  * ``system-status.status`` - The system status of the instance (``ok`` | ``impaired`` | ``initializing`` | ``insufficient-data`` | ``not-applicable`` ). 
   

  



Shorthand Syntax::

    Name=string,Values=string,string ...




JSON Syntax::

  [
    {
      "Name": "string",
      "Values": ["string", ...]
    }
    ...
  ]



``--instance-ids`` (list)


  One or more instance IDs.

   

  Default: Describes all your instances.

   

  Constraints: Maximum 100 explicitly specified instance IDs.

  



Syntax::

  "string" "string" ...



``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--include-all-instances`` | ``--no-include-all-instances`` (boolean)


  When ``true`` , includes the health status for all instances. When ``false`` , includes the health status for running instances only.

   

  Default: ``false``  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe the status of an instance**

This example describes the current status of the specified instance.

Command::

  aws ec2 describe-instance-status --instance-id i-1234567890abcdef0

Output::

  {
      "InstanceStatuses": [
          {
              "InstanceId": "i-1234567890abcdef0",
              "InstanceState": {
                  "Code": 16,
                  "Name": "running"
              },
              "AvailabilityZone": "us-east-1d",
              "SystemStatus": {
                  "Status": "ok",
                  "Details": [
                      {
                          "Status": "passed",
                          "Name": "reachability"
                      }
                  ]
              },
              "InstanceStatus": {
                  "Status": "ok",
                  "Details": [
                      {
                          "Status": "passed",
                          "Name": "reachability"
                      }
                  ]
              }
          }
      ]
  }


======
Output
======

InstanceStatuses -> (list)

  

  One or more instance status descriptions.

  

  (structure)

    

    Describes the status of an instance.

    

    AvailabilityZone -> (string)

      

      The Availability Zone of the instance.

      

      

    Events -> (list)

      

      Any scheduled events associated with the instance.

      

      (structure)

        

        Describes a scheduled event for an instance.

        

        Code -> (string)

          

          The event code.

          

          

        Description -> (string)

          

          A description of the event.

           

          After a scheduled event is completed, it can still be described for up to a week. If the event has been completed, this description starts with the following text: [Completed].

          

          

        NotAfter -> (timestamp)

          

          The latest scheduled end time for the event.

          

          

        NotBefore -> (timestamp)

          

          The earliest scheduled start time for the event.

          

          

        

      

    InstanceId -> (string)

      

      The ID of the instance.

      

      

    InstanceState -> (structure)

      

      The intended state of the instance.  describe-instance-status requires that an instance be in the ``running`` state.

      

      Code -> (integer)

        

        The low byte represents the state. The high byte is an opaque internal value and should be ignored.

         

         
        * ``0`` : ``pending``   
         
        * ``16`` : ``running``   
         
        * ``32`` : ``shutting-down``   
         
        * ``48`` : ``terminated``   
         
        * ``64`` : ``stopping``   
         
        * ``80`` : ``stopped``   
         

        

        

      Name -> (string)

        

        The current state of the instance.

        

        

      

    InstanceStatus -> (structure)

      

      Reports impaired functionality that stems from issues internal to the instance, such as impaired reachability.

      

      Details -> (list)

        

        The system instance health or application instance health.

        

        (structure)

          

          Describes the instance status.

          

          ImpairedSince -> (timestamp)

            

            The time when a status check failed. For an instance that was launched and impaired, this is the time when the instance was launched.

            

            

          Name -> (string)

            

            The type of instance status.

            

            

          Status -> (string)

            

            The status.

            

            

          

        

      Status -> (string)

        

        The status.

        

        

      

    SystemStatus -> (structure)

      

      Reports impaired functionality that stems from issues related to the systems that support an instance, such as hardware failures and network connectivity problems.

      

      Details -> (list)

        

        The system instance health or application instance health.

        

        (structure)

          

          Describes the instance status.

          

          ImpairedSince -> (timestamp)

            

            The time when a status check failed. For an instance that was launched and impaired, this is the time when the instance was launched.

            

            

          Name -> (string)

            

            The type of instance status.

            

            

          Status -> (string)

            

            The status.

            

            

          

        

      Status -> (string)

        

        The status.

        

        

      

    

  

NextToken -> (string)

  

  The token to use to retrieve the next page of results. This value is ``null`` when there are no more results to return.

  

  

