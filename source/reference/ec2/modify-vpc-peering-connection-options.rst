[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 modify-vpc-peering-connection-options:


*************************************
modify-vpc-peering-connection-options
*************************************



===========
Description
===========



Modifies the VPC peering connection options on one side of a VPC peering connection. You can do the following:

 

 
* Enable/disable communication over the peering connection between an EC2-Classic instance that's linked to your VPC (using ClassicLink) and instances in the peer VPC. 
 
* Enable/disable communication over the peering connection between instances in your VPC and an EC2-Classic instance that's linked to the peer VPC. 
 
* Enable/disable a local VPC to resolve public DNS hostnames to private IP addresses when queried from instances in the peer VPC. 
 

 

If the peered VPCs are in different accounts, each owner must initiate a separate request to modify the peering connection options, depending on whether their VPC was the requester or accepter for the VPC peering connection. If the peered VPCs are in the same account, you can modify the requester and accepter options in the same request. To confirm which VPC is the accepter and requester for a VPC peering connection, use the  describe-vpc-peering-connections command.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/ModifyVpcPeeringConnectionOptions>`_


========
Synopsis
========

::

    modify-vpc-peering-connection-options
  [--accepter-peering-connection-options <value>]
  [--dry-run | --no-dry-run]
  [--requester-peering-connection-options <value>]
  --vpc-peering-connection-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--accepter-peering-connection-options`` (structure)


  The VPC peering connection options for the accepter VPC.

  



Shorthand Syntax::

    AllowDnsResolutionFromRemoteVpc=boolean,AllowEgressFromLocalClassicLinkToRemoteVpc=boolean,AllowEgressFromLocalVpcToRemoteClassicLink=boolean




JSON Syntax::

  {
    "AllowDnsResolutionFromRemoteVpc": true|false,
    "AllowEgressFromLocalClassicLinkToRemoteVpc": true|false,
    "AllowEgressFromLocalVpcToRemoteClassicLink": true|false
  }



``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the operation, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--requester-peering-connection-options`` (structure)


  The VPC peering connection options for the requester VPC.

  



Shorthand Syntax::

    AllowDnsResolutionFromRemoteVpc=boolean,AllowEgressFromLocalClassicLinkToRemoteVpc=boolean,AllowEgressFromLocalVpcToRemoteClassicLink=boolean




JSON Syntax::

  {
    "AllowDnsResolutionFromRemoteVpc": true|false,
    "AllowEgressFromLocalClassicLinkToRemoteVpc": true|false,
    "AllowEgressFromLocalVpcToRemoteClassicLink": true|false
  }



``--vpc-peering-connection-id`` (string)


  The ID of the VPC peering connection.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To enable communication over a VPC peering connection from your local ClassicLink connection**

In this example, for peering connection ``pcx-aaaabbb``, the owner of the requester VPC modifies the VPC peering connection options to enable a local ClassicLink connection to communicate with the peer VPC.

Command::

  aws ec2 modify-vpc-peering-connection-options --vpc-peering-connection-id pcx-aaaabbbb --requester-peering-connection-options AllowEgressFromLocalClassicLinkToRemoteVpc=true
  
Output::

  {
    "RequesterPeeringConnectionOptions": {
        "AllowEgressFromLocalClassicLinkToRemoteVpc": true
    }
  }

**To enable communication over a VPC peering connection from your local VPC to a remote ClassicLink connection**

In this example, the owner of the accepter VPC modifies the VPC peering connection options to enable the local VPC to communicate with the ClassicLink connection in the peer VPC. 

Command::

  aws ec2 modify-vpc-peering-connection-options --vpc-peering-connection-id pcx-aaaabbbb --accepter-peering-connection-options AllowEgressFromLocalVpcToRemoteClassicLink=true

Output::

  {
    "AccepterPeeringConnectionOptions": {
      "AllowEgressFromLocalVpcToRemoteClassicLink": true
    }
  }

**To enable DNS resolution support for the VPC peering connection**

In this example, the owner of the requester VPC modifies the VPC peering connection options for ``pcx-aaaabbbb`` to enable the local VPC to resolve public DNS hostnames to private IP addresses when queried from instances in the peer VPC.

Command::

  aws ec2 modify-vpc-peering-connection-options --vpc-peering-connection-id pcx-aaaabbbb --requester-peering-connection-options AllowDnsResolutionFromRemoteVpc=true
  
Output::

  {
    "RequesterPeeringConnectionOptions": {
        "AllowDnsResolutionFromRemoteVpc": true
    }
  }

======
Output
======

AccepterPeeringConnectionOptions -> (structure)

  

  Information about the VPC peering connection options for the accepter VPC.

  

  AllowDnsResolutionFromRemoteVpc -> (boolean)

    

    If true, enables a local VPC to resolve public DNS hostnames to private IP addresses when queried from instances in the peer VPC.

    

    

  AllowEgressFromLocalClassicLinkToRemoteVpc -> (boolean)

    

    If true, enables outbound communication from an EC2-Classic instance that's linked to a local VPC via ClassicLink to instances in a peer VPC.

    

    

  AllowEgressFromLocalVpcToRemoteClassicLink -> (boolean)

    

    If true, enables outbound communication from instances in a local VPC to an EC2-Classic instance that's linked to a peer VPC via ClassicLink.

    

    

  

RequesterPeeringConnectionOptions -> (structure)

  

  Information about the VPC peering connection options for the requester VPC.

  

  AllowDnsResolutionFromRemoteVpc -> (boolean)

    

    If true, enables a local VPC to resolve public DNS hostnames to private IP addresses when queried from instances in the peer VPC.

    

    

  AllowEgressFromLocalClassicLinkToRemoteVpc -> (boolean)

    

    If true, enables outbound communication from an EC2-Classic instance that's linked to a local VPC via ClassicLink to instances in a peer VPC.

    

    

  AllowEgressFromLocalVpcToRemoteClassicLink -> (boolean)

    

    If true, enables outbound communication from instances in a local VPC to an EC2-Classic instance that's linked to a peer VPC via ClassicLink.

    

    

  

