[ :ref:`aws <cli:aws>` . :ref:`directconnect <cli:aws directconnect>` ]

.. _cli:aws directconnect describe-virtual-gateways:


*************************
describe-virtual-gateways
*************************



===========
Description
===========



Returns a list of virtual private gateways owned by the AWS account.

 

You can create one or more AWS Direct Connect private virtual interfaces linking to a virtual private gateway. A virtual private gateway can be managed via Amazon Virtual Private Cloud (VPC) console or the `EC2 CreateVpnGateway`_ action.



========
Synopsis
========

::

    describe-virtual-gateways
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

virtualGateways -> (list)

  

  A list of virtual private gateways.

  

  (structure)

    

    You can create one or more AWS Direct Connect private virtual interfaces linking to your virtual private gateway.

     

    Virtual private gateways can be managed using the Amazon Virtual Private Cloud (Amazon VPC) console or the `Amazon EC2 CreateVpnGateway action`_ .

    

    virtualGatewayId -> (string)

      

      The ID of the virtual private gateway to a VPC. This only applies to private virtual interfaces.

       

      Example: vgw-123er56

      

      

    virtualGatewayState -> (string)

      State of the virtual private gateway. 

       
      * **Pending** : This is the initial state after calling *CreateVpnGateway* .
       
      * **Available** : Ready for use by a private virtual interface.
       
      * **Deleting** : This is the initial state after calling *DeleteVpnGateway* .
       
      * **Deleted** : In this state, a private virtual interface is unable to send traffic over this gateway.
       

      

      

    

  



.. _Amazon EC2 CreateVpnGateway action: http://docs.aws.amazon.com/AWSEC2/latest/APIReference/ApiReference-query-CreateVpnGateway.html
.. _EC2 CreateVpnGateway: http://docs.aws.amazon.com/AWSEC2/latest/APIReference/ApiReference-query-CreateVpnGateway.html
