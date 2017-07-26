[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-reserved-instances-modifications:


*****************************************
describe-reserved-instances-modifications
*****************************************



===========
Description
===========



Describes the modifications made to your Reserved Instances. If no parameter is specified, information about all your Reserved Instances modification requests is returned. If a modification ID is specified, only information about the specific modification is returned.

 

For more information, see `Modifying Reserved Instances <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ri-modifying.html>`_ in the Amazon Elastic Compute Cloud User Guide.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeReservedInstancesModifications>`_


``describe-reserved-instances-modifications`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``ReservedInstancesModifications``


========
Synopsis
========

::

    describe-reserved-instances-modifications
  [--filters <value>]
  [--reserved-instances-modification-ids <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--filters`` (list)


  One or more filters.

   

   
  * ``client-token`` - The idempotency token for the modification request. 
   
  * ``create-date`` - The time when the modification request was created. 
   
  * ``effective-date`` - The time when the modification becomes effective. 
   
  * ``modification-result.reserved-instances-id`` - The ID for the Reserved Instances created as part of the modification request. This ID is only available when the status of the modification is ``fulfilled`` . 
   
  * ``modification-result.target-configuration.availability-zone`` - The Availability Zone for the new Reserved Instances. 
   
  * ``modification-result.target-configuration.instance-count`` - The number of new Reserved Instances. 
   
  * ``modification-result.target-configuration.instance-type`` - The instance type of the new Reserved Instances. 
   
  * ``modification-result.target-configuration.platform`` - The network platform of the new Reserved Instances (``EC2-Classic`` | ``EC2-VPC`` ). 
   
  * ``reserved-instances-id`` - The ID of the Reserved Instances modified. 
   
  * ``reserved-instances-modification-id`` - The ID of the modification request. 
   
  * ``status`` - The status of the Reserved Instances modification request (``processing`` | ``fulfilled`` | ``failed`` ). 
   
  * ``status-message`` - The reason for the status. 
   
  * ``update-date`` - The time when the modification request was last updated. 
   

  



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



``--reserved-instances-modification-ids`` (list)


  IDs for the submitted modification request.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe Reserved Instances modifications**

This example command describes all the Reserved Instances modification requests that have been submitted for your account.

Command::

  aws ec2 describe-reserved-instances-modifications

Output::

  {
      "ReservedInstancesModifications": [
          {
              "Status": "fulfilled",
              "ModificationResults": [
                  {
                      "ReservedInstancesId": "93bbbca2-62f1-4d9d-b225-16bada29e6c7",
                      "TargetConfiguration": {
                          "AvailabilityZone": "us-east-1b",
                          "InstanceType": "m1.large",
                          "InstanceCount": 3
                      }
                  },
                  {
                       "ReservedInstancesId": "1ba8e2e3-aabb-46c3-bcf5-3fe2fda922e6",
                       "TargetConfiguration": {
                           "AvailabilityZone": "us-east-1d",
                           "InstanceType": "m1.xlarge",
                           "InstanceCount": 1
                       }
                   }
              ],
              "EffectiveDate": "2015-08-12T17:00:00.000Z",
              "CreateDate": "2015-08-12T17:52:52.630Z",
              "UpdateDate": "2015-08-12T18:08:06.698Z",
              "ClientToken": "c9adb218-3222-4889-8216-0cf0e52dc37e:
              "ReservedInstancesModificationId": "rimod-d3ed4335-b1d3-4de6-ab31-0f13aaf46687",
              "ReservedInstancesIds": [
                  {
                      "ReservedInstancesId": "b847fa93-e282-4f55-b59a-1342f5bd7c02"
                  }
              ]
          }
      ]
  }




======
Output
======

NextToken -> (string)

  

  The token to use to retrieve the next page of results. This value is ``null`` when there are no more results to return.

  

  

ReservedInstancesModifications -> (list)

  

  The Reserved Instance modification information.

  

  (structure)

    

    Describes a Reserved Instance modification.

    

    ClientToken -> (string)

      

      A unique, case-sensitive key supplied by the client to ensure that the request is idempotent. For more information, see `Ensuring Idempotency <http://docs.aws.amazon.com/AWSEC2/latest/APIReference/Run_Instance_Idempotency.html>`_ .

      

      

    CreateDate -> (timestamp)

      

      The time when the modification request was created.

      

      

    EffectiveDate -> (timestamp)

      

      The time for the modification to become effective.

      

      

    ModificationResults -> (list)

      

      Contains target configurations along with their corresponding new Reserved Instance IDs.

      

      (structure)

        

        Describes the modification request/s.

        

        ReservedInstancesId -> (string)

          

          The ID for the Reserved Instances that were created as part of the modification request. This field is only available when the modification is fulfilled.

          

          

        TargetConfiguration -> (structure)

          

          The target Reserved Instances configurations supplied as part of the modification request.

          

          AvailabilityZone -> (string)

            

            The Availability Zone for the modified Reserved Instances.

            

            

          InstanceCount -> (integer)

            

            The number of modified Reserved Instances.

            

            

          InstanceType -> (string)

            

            The instance type for the modified Reserved Instances.

            

            

          Platform -> (string)

            

            The network platform of the modified Reserved Instances, which is either EC2-Classic or EC2-VPC.

            

            

          Scope -> (string)

            

            Whether the Reserved Instance is applied to instances in a region or instances in a specific Availability Zone.

            

            

          

        

      

    ReservedInstancesIds -> (list)

      

      The IDs of one or more Reserved Instances.

      

      (structure)

        

        Describes the ID of a Reserved Instance.

        

        ReservedInstancesId -> (string)

          

          The ID of the Reserved Instance.

          

          

        

      

    ReservedInstancesModificationId -> (string)

      

      A unique ID for the Reserved Instance modification.

      

      

    Status -> (string)

      

      The status of the Reserved Instances modification request.

      

      

    StatusMessage -> (string)

      

      The reason for the status.

      

      

    UpdateDate -> (timestamp)

      

      The time when the modification request was last updated.

      

      

    

  

