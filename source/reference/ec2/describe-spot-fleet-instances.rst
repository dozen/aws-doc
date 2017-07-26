[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-spot-fleet-instances:


*****************************
describe-spot-fleet-instances
*****************************



===========
Description
===========



Describes the running instances for the specified Spot fleet.



========
Synopsis
========

::

    describe-spot-fleet-instances
  [--dry-run | --no-dry-run]
  --spot-fleet-request-id <value>
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--spot-fleet-request-id`` (string)


  The ID of the Spot fleet request.

  

``--next-token`` (string)


  The token for the next set of results.

  

``--max-results`` (integer)


  The maximum number of results to return in a single call. Specify a value between 1 and 1000. The default value is 1000. To retrieve the remaining results, make another call with the returned ``NextToken`` value.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To describe the Spot Instances associated with a Spot fleet**

This example command lists the Spot instances associated with the specified Spot fleet.

Command::

  aws ec2 describe-spot-fleet-instances --spot-fleet-request-id sfr-73fbd2ce-aa30-494c-8788-1cee4EXAMPLE

Output::

  {
    "ActiveInstances": [
        {
            "InstanceId": "i-3852c1cf",
            "InstanceType": "m3.medium",
            "SpotInstanceRequestId": "sir-08b93456"
        },
        ...
    ],
    "SpotFleetRequestId": "sfr-73fbd2ce-aa30-494c-8788-1cee4EXAMPLE"
  }


======
Output
======

SpotFleetRequestId -> (string)

  

  The ID of the Spot fleet request.

  

  

ActiveInstances -> (list)

  

  The running instances. Note that this list is refreshed periodically and might be out of date.

  

  (structure)

    

    Describes a running instance in a Spot fleet.

    

    InstanceType -> (string)

      

      The instance type.

      

      

    InstanceId -> (string)

      

      The ID of the instance.

      

      

    SpotInstanceRequestId -> (string)

      

      The ID of the Spot instance request.

      

      

    

  

NextToken -> (string)

  

  The token required to retrieve the next set of results. This value is ``null`` when there are no more results to return.

  

  

