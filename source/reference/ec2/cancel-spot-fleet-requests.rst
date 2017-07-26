[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 cancel-spot-fleet-requests:


**************************
cancel-spot-fleet-requests
**************************



===========
Description
===========



Cancels the specified Spot fleet requests.

 

After you cancel a Spot fleet request, the Spot fleet launches no new Spot instances. You must specify whether the Spot fleet should also terminate its Spot instances. If you terminate the instances, the Spot fleet request enters the ``cancelled_terminating`` state. Otherwise, the Spot fleet request enters the ``cancelled_running`` state and the instances continue to run until they are interrupted or you terminate them manually.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/CancelSpotFleetRequests>`_


========
Synopsis
========

::

    cancel-spot-fleet-requests
  [--dry-run | --no-dry-run]
  --spot-fleet-request-ids <value>
  --terminate-instances | --no-terminate-instances
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--spot-fleet-request-ids`` (list)


  The IDs of the Spot fleet requests.

  



Syntax::

  "string" "string" ...



``--terminate-instances`` | ``--no-terminate-instances`` (boolean)


  Indicates whether to terminate instances for a Spot fleet request if it is canceled successfully.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To cancel Spot fleet requests**

This example command cancels a Spot fleet request and terminates the associated Spot Instances.

Command::

  aws ec2 cancel-spot-fleet-requests --spot-fleet-request-ids sfr-73fbd2ce-aa30-494c-8788-1cee4EXAMPLE --terminate-instances

Output::

  {
    "SuccessfulFleetRequests": [
        {
            "SpotFleetRequestId": "sfr-73fbd2ce-aa30-494c-8788-1cee4EXAMPLE",
            "CurrentSpotFleetRequestState": "cancelled_running",
            "PreviousSpotFleetRequestState": "active"
        }
    ],
    "UnsuccessfulFleetRequests": []
  }

This example command cancels a Spot fleet request without terminating the associated Spot Instances.

Command::

  aws ec2 cancel-spot-fleet-requests --spot-fleet-request-ids sfr-73fbd2ce-aa30-494c-8788-1cee4EXAMPLE --no-terminate-instances

Output::

  {
    "SuccessfulFleetRequests": [
        {
            "SpotFleetRequestId": "sfr-73fbd2ce-aa30-494c-8788-1cee4EXAMPLE",
            "CurrentSpotFleetRequestState": "cancelled_terminating",
            "PreviousSpotFleetRequestState": "active"
        }
    ],
    "UnsuccessfulFleetRequests": []  
  }


======
Output
======

SuccessfulFleetRequests -> (list)

  

  Information about the Spot fleet requests that are successfully canceled.

  

  (structure)

    

    Describes a Spot fleet request that was successfully canceled.

    

    CurrentSpotFleetRequestState -> (string)

      

      The current state of the Spot fleet request.

      

      

    PreviousSpotFleetRequestState -> (string)

      

      The previous state of the Spot fleet request.

      

      

    SpotFleetRequestId -> (string)

      

      The ID of the Spot fleet request.

      

      

    

  

UnsuccessfulFleetRequests -> (list)

  

  Information about the Spot fleet requests that are not successfully canceled.

  

  (structure)

    

    Describes a Spot fleet request that was not successfully canceled.

    

    Error -> (structure)

      

      The error.

      

      Code -> (string)

        

        The error code.

        

        

      Message -> (string)

        

        The description for the error code.

        

        

      

    SpotFleetRequestId -> (string)

      

      The ID of the Spot fleet request.

      

      

    

  

