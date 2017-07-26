[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-hosts:


**************
describe-hosts
**************



===========
Description
===========



Describes one or more of your Dedicated Hosts.

 

The results describe only the Dedicated Hosts in the region you're currently using. All listed instances consume capacity on your Dedicated Host. Dedicated Hosts that have recently been released will be listed with the state ``released`` .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeHosts>`_


========
Synopsis
========

::

    describe-hosts
  [--filter <value>]
  [--host-ids <value>]
  [--max-results <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--filter`` (list)


  One or more filters.

   

   
  * ``instance-type`` - The instance type size that the Dedicated Host is configured to support. 
   
  * ``auto-placement`` - Whether auto-placement is enabled or disabled (``on`` | ``off`` ). 
   
  * ``host-reservation-id`` - The ID of the reservation assigned to this host. 
   
  * ``client-token`` - The idempotency token you provided when you launched the instance 
   
  * ``state`` - The allocation state of the Dedicated Host (``available`` | ``under-assessment`` | ``permanent-failure`` | ``released`` | ``released-permanent-failure`` ). 
   
  * ``availability-zone`` - The Availability Zone of the host. 
   

  



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



``--host-ids`` (list)


  The IDs of the Dedicated Hosts. The IDs are used for targeted instance launches.

  



Syntax::

  "string" "string" ...



``--max-results`` (integer)


  The maximum number of results to return for the request in a single page. The remaining results can be seen by sending another request with the returned ``nextToken`` value. This value can be between 5 and 500; if ``maxResults`` is given a larger value than 500, you will receive an error. You cannot specify this parameter and the host IDs parameter in the same request.

  

``--next-token`` (string)


  The token to retrieve the next page of results.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe Dedicated hosts in your account and generate a machine-readable list**

To output a list of Dedicated host IDs in JSON (comma separated).

Command::

  aws ec2 describe-hosts --query 'Hosts[].HostId' --output json

Output::

  [
  "h-085664df5899941c",
  "h-056c1b0724170dc38"
  ]

To output a list of Dedicated host IDs in plaintext (comma separated).

Command::

  aws ec2 describe-hosts --query 'Hosts[].HostId' --output text

Output::
h-085664df5899941c
h-056c1b0724170dc38

**To describe available Dedicated hosts in your account**

Command::

  aws ec2 describe-hosts --filter "Name=state,Values=available"

Output::

  { 
    "Hosts":  [
        {
            "HostId": "h-085664df5899941c"
            "HostProperties: {
                "Cores": 20,
                 "Sockets": 2,
                  "InstanceType": "m3.medium".
                  "TotalVCpus": 32
             },
             "Instances": [],
              "State": "available",
              "AvailabilityZone": "us-east-1b",
              "AvailableCapacity": {
                  "AvailableInstanceCapacity": [
                      {
                            "AvailableCapacity": 32,
                            "InstanceType": "m3.medium",
                            "TotalCapacity": 32
                      }
                   ],
                   "AvailableVCpus": 32
              },
              "AutoPlacement": "off"
       }
    ]
  }
  


======
Output
======

Hosts -> (list)

  

  Information about the Dedicated Hosts.

  

  (structure)

    

    Describes the properties of the Dedicated Host.

    

    AutoPlacement -> (string)

      

      Whether auto-placement is on or off.

      

      

    AvailabilityZone -> (string)

      

      The Availability Zone of the Dedicated Host.

      

      

    AvailableCapacity -> (structure)

      

      The number of new instances that can be launched onto the Dedicated Host.

      

      AvailableInstanceCapacity -> (list)

        

        The total number of instances that the Dedicated Host supports.

        

        (structure)

          

          Information about the instance type that the Dedicated Host supports.

          

          AvailableCapacity -> (integer)

            

            The number of instances that can still be launched onto the Dedicated Host.

            

            

          InstanceType -> (string)

            

            The instance type size supported by the Dedicated Host.

            

            

          TotalCapacity -> (integer)

            

            The total number of instances that can be launched onto the Dedicated Host.

            

            

          

        

      AvailableVCpus -> (integer)

        

        The number of vCPUs available on the Dedicated Host.

        

        

      

    ClientToken -> (string)

      

      Unique, case-sensitive identifier you provide to ensure idempotency of the request. For more information, see `How to Ensure Idempotency <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Run_Instance_Idempotency.html>`_ in the *Amazon Elastic Compute Cloud User Guide* . 

      

      

    HostId -> (string)

      

      The ID of the Dedicated Host.

      

      

    HostProperties -> (structure)

      

      The hardware specifications of the Dedicated Host.

      

      Cores -> (integer)

        

        The number of cores on the Dedicated Host.

        

        

      InstanceType -> (string)

        

        The instance type size that the Dedicated Host supports (for example, ``m3.medium`` ).

        

        

      Sockets -> (integer)

        

        The number of sockets on the Dedicated Host.

        

        

      TotalVCpus -> (integer)

        

        The number of vCPUs on the Dedicated Host.

        

        

      

    HostReservationId -> (string)

      

      The reservation ID of the Dedicated Host. This returns a ``null`` response if the Dedicated Host doesn't have an associated reservation.

      

      

    Instances -> (list)

      

      The IDs and instance type that are currently running on the Dedicated Host.

      

      (structure)

        

        Describes an instance running on a Dedicated Host.

        

        InstanceId -> (string)

          

          the IDs of instances that are running on the Dedicated Host.

          

          

        InstanceType -> (string)

          

          The instance type size (for example, ``m3.medium`` ) of the running instance.

          

          

        

      

    State -> (string)

      

      The Dedicated Host's state.

      

      

    

  

NextToken -> (string)

  

  The token to use to retrieve the next page of results. This value is ``null`` when there are no more results to return.

  

  

