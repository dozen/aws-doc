[ :ref:`aws <cli:aws>` . :ref:`emr <cli:aws emr>` ]

.. _cli:aws emr list-instances:


**************
list-instances
**************



===========
Description
===========



Provides information about the cluster instances that Amazon EMR provisions on behalf of a user when it creates the cluster. For example, this operation indicates when the EC2 instances reach the Ready state, when instances become available to Amazon EMR to use for jobs, and the IP addresses for cluster instances, etc. 



``list-instances`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Instances``


========
Synopsis
========

::

    list-instances
  --cluster-id <value>
  [--instance-group-id <value>]
  [--instance-group-types <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cluster-id`` (string)


  The identifier of the cluster for which to list the instances.

  

``--instance-group-id`` (string)


  The identifier of the instance group for which to list the instances.

  

``--instance-group-types`` (list)


  The type of instance group for which to list the instances.

  



Syntax::

  "string" "string" ...

  Where valid values are:
    MASTER
    CORE
    TASK





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

The following command lists all of the instances in a cluster with the cluster ID ``j-3C6XNQ39VR9WL``::

  aws emr list-instances --cluster-id j-3C6XNQ39VR9WL

Output::

  {
      "Instances": [
           {
              "Status": {
                  "Timeline": {
                      "ReadyDateTime": 1433200400.03,
                      "CreationDateTime": 1433199960.152
                  },
                  "State": "RUNNING",
                  "StateChangeReason": {}
              },
              "Ec2InstanceId": "i-f19ecfee",
              "PublicDnsName": "ec2-52-52-41-150.us-west-2.compute.amazonaws.com",
              "PrivateDnsName": "ip-172-21-11-216.us-west-2.compute.internal",
              "PublicIpAddress": "52.52.41.150",
              "Id": "ci-3NNHQUQ2TWB6Y",
              "PrivateIpAddress": "172.21.11.216"
          },
          {
              "Status": {
                  "Timeline": {
                      "ReadyDateTime": 1433200400.031,
                      "CreationDateTime": 1433199949.102
                  },
                  "State": "RUNNING",
                  "StateChangeReason": {}
              },
              "Ec2InstanceId": "i-1feee4c2",
              "PublicDnsName": "ec2-52-63-246-32.us-west-2.compute.amazonaws.com",
              "PrivateDnsName": "ip-172-31-24-130.us-west-2.compute.internal",
              "PublicIpAddress": "52.63.246.32",
              "Id": "ci-GAOCMKNKDCV7",
              "PrivateIpAddress": "172.21.11.215"
          },
          {
              "Status": {
                  "Timeline": {
                      "ReadyDateTime": 1433200400.031,
                      "CreationDateTime": 1433199949.102
                  },
                  "State": "RUNNING",
                  "StateChangeReason": {}
              },
              "Ec2InstanceId": "i-15cfeee3",
              "PublicDnsName": "ec2-52-25-246-63.us-west-2.compute.amazonaws.com",
              "PrivateDnsName": "ip-172-31-24-129.us-west-2.compute.internal",
              "PublicIpAddress": "52.25.246.63",
              "Id": "ci-2W3TDFFB47UAD",
              "PrivateIpAddress": "172.21.11.214"
          }
      ]
  }


======
Output
======

Instances -> (list)

  

  The list of instances for the cluster and given filters.

  

  (structure)

    

    Represents an EC2 instance provisioned as part of cluster.

    

    Id -> (string)

      

      The unique identifier for the instance in Amazon EMR.

      

      

    Ec2InstanceId -> (string)

      

      The unique identifier of the instance in Amazon EC2.

      

      

    PublicDnsName -> (string)

      

      The public DNS name of the instance.

      

      

    PublicIpAddress -> (string)

      

      The public IP address of the instance.

      

      

    PrivateDnsName -> (string)

      

      The private DNS name of the instance.

      

      

    PrivateIpAddress -> (string)

      

      The private IP address of the instance.

      

      

    Status -> (structure)

      

      The current status of the instance.

      

      State -> (string)

        

        The current state of the instance.

        

        

      StateChangeReason -> (structure)

        

        The details of the status change reason for the instance.

        

        Code -> (string)

          

          The programmable code for the state change reason.

          

          

        Message -> (string)

          

          The status change reason description.

          

          

        

      Timeline -> (structure)

        

        The timeline of the instance status over time.

        

        CreationDateTime -> (timestamp)

          

          The creation date and time of the instance.

          

          

        ReadyDateTime -> (timestamp)

          

          The date and time when the instance was ready to perform tasks.

          

          

        EndDateTime -> (timestamp)

          

          The date and time when the instance was terminated.

          

          

        

      

    InstanceGroupId -> (string)

      

      The identifier of the instance group to which this instance belongs.

      

      

    EbsVolumes -> (list)

      

      The list of EBS volumes that are attached to this instance.

      

      (structure)

        

        EBS block device that's attached to an EC2 instance.

        

        Device -> (string)

          

          The device name that is exposed to the instance, such as /dev/sdh.

          

          

        VolumeId -> (string)

          

          The volume identifier of the EBS volume.

          

          

        

      

    

  

Marker -> (string)

  

  The pagination token that indicates the next set of results to retrieve.

  

  

