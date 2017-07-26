[ :ref:`aws <cli:aws>` . :ref:`directconnect <cli:aws directconnect>` ]

.. _cli:aws directconnect describe-virtual-gateways:


*************************
describe-virtual-gateways
*************************



===========
Description
===========



Returns a list of virtual private gateways owned by the AWS account.

 

You can create one or more AWS Direct Connect private virtual interfaces linking to a virtual private gateway. A virtual private gateway can be managed via Amazon Virtual Private Cloud (VPC) console or the `EC2 CreateVpnGateway <http://docs.aws.amazon.com/AWSEC2/latest/APIReference/ApiReference-query-CreateVpnGateway.html>`_ action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/directconnect-2012-10-25/DescribeVirtualGateways>`_


========
Synopsis
========

::

    describe-virtual-gateways
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To list virtual private gateways**

The following ``describe-virtual-gateways`` command lists virtual private gateways owned by your AWS account::

  aws directconnect describe-virtual-gateways

Output::

  {
      "virtualGateways": [
          {
              "virtualGatewayId": "vgw-aba37db6", 
              "virtualGatewayState": "available"
          }
      ]
  }

======
Output
======

virtualGateways -> (list)

  

  A list of virtual private gateways.

  

  (structure)

    

    You can create one or more AWS Direct Connect private virtual interfaces linking to your virtual private gateway.

     

    Virtual private gateways can be managed using the Amazon Virtual Private Cloud (Amazon VPC) console or the `Amazon EC2 CreateVpnGateway action <http://docs.aws.amazon.com/AWSEC2/latest/APIReference/ApiReference-query-CreateVpnGateway.html>`_ .

    

    virtualGatewayId -> (string)

      

      The ID of the virtual private gateway to a VPC. This only applies to private virtual interfaces.

       

      Example: vgw-123er56

      

      

    virtualGatewayState -> (string)

      

      State of the virtual private gateway.

       

       
      * **Pending** : This is the initial state after calling *CreateVpnGateway* . 
       
      * **Available** : Ready for use by a private virtual interface. 
       
      * **Deleting** : This is the initial state after calling *DeleteVpnGateway* . 
       
      * **Deleted** : In this state, a private virtual interface is unable to send traffic over this gateway. 
       

      

      

    

  

