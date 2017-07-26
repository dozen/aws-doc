[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 cancel-spot-instance-requests:


*****************************
cancel-spot-instance-requests
*****************************



===========
Description
===========



Cancels one or more Spot instance requests. Spot instances are instances that Amazon EC2 starts on your behalf when the bid price that you specify exceeds the current Spot price. Amazon EC2 periodically sets the Spot price based on available Spot instance capacity and current Spot instance requests. For more information, see `Spot Instance Requests <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/spot-requests.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .

 

.. warning::

   

  Canceling a Spot instance request does not terminate running Spot instances associated with the request.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/CancelSpotInstanceRequests>`_


========
Synopsis
========

::

    cancel-spot-instance-requests
  [--dry-run | --no-dry-run]
  --spot-instance-request-ids <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--spot-instance-request-ids`` (list)


  One or more Spot instance request IDs.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To cancel Spot Instance requests**

This example command cancels a Spot Instance request.

Command::

  aws ec2 cancel-spot-instance-requests --spot-instance-request-ids sir-08b93456

Output::

  {
      "CancelledSpotInstanceRequests": [
          {
              "State": "cancelled",
              "SpotInstanceRequestId": "sir-08b93456"
          }
      ]
  }



======
Output
======

CancelledSpotInstanceRequests -> (list)

  

  One or more Spot instance requests.

  

  (structure)

    

    Describes a request to cancel a Spot instance.

    

    SpotInstanceRequestId -> (string)

      

      The ID of the Spot instance request.

      

      

    State -> (string)

      

      The state of the Spot instance request.

      

      

    

  

