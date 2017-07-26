[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` . :ref:`wait <cli:aws ec2 wait>` ]

.. _cli:aws ec2 wait vpn-connection-available:


************************
vpn-connection-available
************************



===========
Description
===========

Wait until JMESPath query VpnConnections[].State returns available for all elements when polling with ``describe-vpn-connections``. It will poll every 15 seconds until a successful state has been reached. This will exit with a return code of 255 after 40 failed checks.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeVpnConnections>`_


========
Synopsis
========

::

    vpn-connection-available
  [--filters <value>]
  [--vpn-connection-ids <value>]
  [--dry-run | --no-dry-run]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--filters`` (list)


  One or more filters.

   

   
  * ``customer-gateway-configuration`` - The configuration information for the customer gateway. 
   
  * ``customer-gateway-id`` - The ID of a customer gateway associated with the VPN connection. 
   
  * ``state`` - The state of the VPN connection (``pending`` | ``available`` | ``deleting`` | ``deleted`` ). 
   
  * ``option.static-routes-only`` - Indicates whether the connection has static routes only. Used for devices that do not support Border Gateway Protocol (BGP). 
   
  * ``route.destination-cidr-block`` - The destination CIDR block. This corresponds to the subnet used in a customer data center. 
   
  * ``bgp-asn`` - The BGP Autonomous System Number (ASN) associated with a BGP device. 
   
  * ``tag`` :*key* =*value* - The key/value combination of a tag assigned to the resource. Specify the key of the tag in the filter name and the value of the tag in the filter value. For example, for the tag Purpose=X, specify ``tag:Purpose`` for the filter name and ``X`` for the filter value. 
   
  * ``tag-key`` - The key of a tag assigned to the resource. This filter is independent of the ``tag-value`` filter. For example, if you use both the filter "tag-key=Purpose" and the filter "tag-value=X", you get any resources assigned both the tag key Purpose (regardless of what the tag's value is), and the tag value X (regardless of what the tag's key is). If you want to list only resources where Purpose is X, see the ``tag`` :*key* =*value* filter. 
   
  * ``tag-value`` - The value of a tag assigned to the resource. This filter is independent of the ``tag-key`` filter. 
   
  * ``type`` - The type of VPN connection. Currently the only supported type is ``ipsec.1`` . 
   
  * ``vpn-connection-id`` - The ID of the VPN connection. 
   
  * ``vpn-gateway-id`` - The ID of a virtual private gateway associated with the VPN connection. 
   

  



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



``--vpn-connection-ids`` (list)


  One or more VPN connection IDs.

   

  Default: Describes your VPN connections.

  



Syntax::

  "string" "string" ...



``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None