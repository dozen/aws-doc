[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-nat-gateways:


*********************
describe-nat-gateways
*********************



===========
Description
===========



Describes one or more of the your NAT gateways.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeNatGateways>`_


``describe-nat-gateways`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``NatGateways``


========
Synopsis
========

::

    describe-nat-gateways
  [--filter <value>]
  [--nat-gateway-ids <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--filter`` (list)


  One or more filters.

   

   
  * ``nat-gateway-id`` - The ID of the NAT gateway. 
   
  * ``state`` - The state of the NAT gateway (``pending`` | ``failed`` | ``available`` | ``deleting`` | ``deleted`` ). 
   
  * ``subnet-id`` - The ID of the subnet in which the NAT gateway resides. 
   
  * ``vpc-id`` - The ID of the VPC in which the NAT gateway resides. 
   

  



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



``--nat-gateway-ids`` (list)


  One or more NAT gateway IDs.

  



Syntax::

  "string" "string" ...



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

**To describe your NAT gateways**

This example describes all of your NAT gateways.

Command::

  aws ec2 describe-nat-gateways

Output::

  {
    "NatGateways": [
      {
        "NatGatewayAddresses": [
          {
            "PublicIp": "198.11.222.333", 
            "NetworkInterfaceId": "eni-9dec76cd", 
            "AllocationId": "eipalloc-89c620ec", 
            "PrivateIp": "10.0.0.149"
          }
        ], 
        "VpcId": "vpc-1a2b3c4d", 
        "State": "available", 
        "NatGatewayId": "nat-05dba92075d71c408", 
        "SubnetId": "subnet-847e4dc2", 
        "CreateTime": "2015-12-01T12:26:55.983Z"
      }, 
      {
        "NatGatewayAddresses": [
          {
            "PublicIp": "1.2.3.12", 
            "NetworkInterfaceId": "eni-71ec7621", 
            "AllocationId": "eipalloc-5d42583f", 
            "PrivateIp": "10.0.0.77"
          }
        ], 
        "VpcId": "vpc-11aa22bb", 
        "State": "deleting", 
        "NatGatewayId": "nat-0a93acc57881d4199", 
        "SubnetId": "subnet-7f7e4d39", 
        "DeleteTime": "2015-12-17T12:26:14.564Z", 
        "CreateTime": "2015-12-01T12:09:22.040Z"
      }
    ]
  }

======
Output
======

NatGateways -> (list)

  

  Information about the NAT gateways.

  

  (structure)

    

    Describes a NAT gateway.

    

    CreateTime -> (timestamp)

      

      The date and time the NAT gateway was created.

      

      

    DeleteTime -> (timestamp)

      

      The date and time the NAT gateway was deleted, if applicable.

      

      

    FailureCode -> (string)

      

      If the NAT gateway could not be created, specifies the error code for the failure. (``InsufficientFreeAddressesInSubnet`` | ``Gateway.NotAttached`` | ``InvalidAllocationID.NotFound`` | ``Resource.AlreadyAssociated`` | ``InternalError`` | ``InvalidSubnetID.NotFound`` )

      

      

    FailureMessage -> (string)

      

      If the NAT gateway could not be created, specifies the error message for the failure, that corresponds to the error code.

       

       
      * For InsufficientFreeAddressesInSubnet: "Subnet has insufficient free addresses to create this NAT gateway" 
       
      * For Gateway.NotAttached: "Network vpc-xxxxxxxx has no Internet gateway attached" 
       
      * For InvalidAllocationID.NotFound: "Elastic IP address eipalloc-xxxxxxxx could not be associated with this NAT gateway" 
       
      * For Resource.AlreadyAssociated: "Elastic IP address eipalloc-xxxxxxxx is already associated" 
       
      * For InternalError: "Network interface eni-xxxxxxxx, created and used internally by this NAT gateway is in an invalid state. Please try again." 
       
      * For InvalidSubnetID.NotFound: "The specified subnet subnet-xxxxxxxx does not exist or could not be found." 
       

      

      

    NatGatewayAddresses -> (list)

      

      Information about the IP addresses and network interface associated with the NAT gateway.

      

      (structure)

        

        Describes the IP addresses and network interface associated with a NAT gateway.

        

        AllocationId -> (string)

          

          The allocation ID of the Elastic IP address that's associated with the NAT gateway.

          

          

        NetworkInterfaceId -> (string)

          

          The ID of the network interface associated with the NAT gateway.

          

          

        PrivateIp -> (string)

          

          The private IP address associated with the Elastic IP address.

          

          

        PublicIp -> (string)

          

          The Elastic IP address associated with the NAT gateway.

          

          

        

      

    NatGatewayId -> (string)

      

      The ID of the NAT gateway.

      

      

    ProvisionedBandwidth -> (structure)

      

      Reserved. If you need to sustain traffic greater than the `documented limits <http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/vpc-nat-gateway.html>`_ , contact us through the `Support Center <https://console.aws.amazon.com/support/home?>`_ .

      

      ProvisionTime -> (timestamp)

        

        Reserved. If you need to sustain traffic greater than the `documented limits <http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/vpc-nat-gateway.html>`_ , contact us through the `Support Center <https://console.aws.amazon.com/support/home?>`_ .

        

        

      Provisioned -> (string)

        

        Reserved. If you need to sustain traffic greater than the `documented limits <http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/vpc-nat-gateway.html>`_ , contact us through the `Support Center <https://console.aws.amazon.com/support/home?>`_ .

        

        

      RequestTime -> (timestamp)

        

        Reserved. If you need to sustain traffic greater than the `documented limits <http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/vpc-nat-gateway.html>`_ , contact us through the `Support Center <https://console.aws.amazon.com/support/home?>`_ .

        

        

      Requested -> (string)

        

        Reserved. If you need to sustain traffic greater than the `documented limits <http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/vpc-nat-gateway.html>`_ , contact us through the `Support Center <https://console.aws.amazon.com/support/home?>`_ .

        

        

      Status -> (string)

        

        Reserved. If you need to sustain traffic greater than the `documented limits <http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/vpc-nat-gateway.html>`_ , contact us through the `Support Center <https://console.aws.amazon.com/support/home?>`_ .

        

        

      

    State -> (string)

      

      The state of the NAT gateway.

       

       
      * ``pending`` : The NAT gateway is being created and is not ready to process traffic. 
       
      * ``failed`` : The NAT gateway could not be created. Check the ``failureCode`` and ``failureMessage`` fields for the reason. 
       
      * ``available`` : The NAT gateway is able to process traffic. This status remains until you delete the NAT gateway, and does not indicate the health of the NAT gateway. 
       
      * ``deleting`` : The NAT gateway is in the process of being terminated and may still be processing traffic. 
       
      * ``deleted`` : The NAT gateway has been terminated and is no longer processing traffic. 
       

      

      

    SubnetId -> (string)

      

      The ID of the subnet in which the NAT gateway is located.

      

      

    VpcId -> (string)

      

      The ID of the VPC in which the NAT gateway is located.

      

      

    

  

NextToken -> (string)

  

  The token to use to retrieve the next page of results. This value is ``null`` when there are no more results to return.

  

  

