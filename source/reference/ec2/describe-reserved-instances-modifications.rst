[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-reserved-instances-modifications:


*****************************************
describe-reserved-instances-modifications
*****************************************



===========
Description
===========



Describes the modifications made to your Reserved Instances. If no parameter is specified, information about all your Reserved Instances modification requests is returned. If a modification ID is specified, only information about the specific modification is returned.

 

For more information, see `Modifying Reserved Instances`_ in the Amazon Elastic Compute Cloud User Guide.



``describe-reserved-instances-modifications`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``ReservedInstancesModifications``


========
Synopsis
========

::

    describe-reserved-instances-modifications
  [--reserved-instances-modification-ids <value>]
  [--filters <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--reserved-instances-modification-ids`` (list)


  IDs for the submitted modification request.

  



Syntax::

  "string" "string" ...



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



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

ReservedInstancesModifications -> (list)

  

  The Reserved Instance modification information.

  

  (structure)

    

    Describes a Reserved Instance modification.

    

    ReservedInstancesModificationId -> (string)

      

      A unique ID for the Reserved Instance modification.

      

      

    ReservedInstancesIds -> (list)

      

      The IDs of one or more Reserved Instances.

      

      (structure)

        

        Describes the ID of a Reserved Instance.

        

        ReservedInstancesId -> (string)

          

          The ID of the Reserved Instance.

          

          

        

      

    ModificationResults -> (list)

      

      Contains target configurations along with their corresponding new Reserved Instance IDs.

      

      (structure)

        

        ReservedInstancesId -> (string)

          

          The ID for the Reserved Instances that were created as part of the modification request. This field is only available when the modification is fulfilled.

          

          

        TargetConfiguration -> (structure)

          

          The target Reserved Instances configurations supplied as part of the modification request.

          

          AvailabilityZone -> (string)

            

            The Availability Zone for the modified Reserved Instances.

            

            

          Platform -> (string)

            

            The network platform of the modified Reserved Instances, which is either EC2-Classic or EC2-VPC.

            

            

          InstanceCount -> (integer)

            

            The number of modified Reserved Instances.

            

            

          InstanceType -> (string)

            

            The instance type for the modified Reserved Instances.

            

            

          

        

      

    CreateDate -> (timestamp)

      

      The time when the modification request was created.

      

      

    UpdateDate -> (timestamp)

      

      The time when the modification request was last updated.

      

      

    EffectiveDate -> (timestamp)

      

      The time for the modification to become effective.

      

      

    Status -> (string)

      

      The status of the Reserved Instances modification request.

      

      

    StatusMessage -> (string)

      

      The reason for the status.

      

      

    ClientToken -> (string)

      

      A unique, case-sensitive key supplied by the client to ensure that the request is idempotent. For more information, see `Ensuring Idempotency`_ .

      

      

    

  

NextToken -> (string)

  

  The token to use to retrieve the next page of results. This value is ``null`` when there are no more results to return.

  

  



.. _Ensuring Idempotency: http://docs.aws.amazon.com/AWSEC2/latest/APIReference/Run_Instance_Idempotency.html
.. _Modifying Reserved Instances: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ri-modifying.html
