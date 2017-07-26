[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-spot-fleet-instances:


*****************************
describe-spot-fleet-instances
*****************************



===========
Description
===========



Describes the running instances for the specified Spot fleet.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeSpotFleetInstances>`_


========
Synopsis
========

::

    describe-spot-fleet-instances
  [--dry-run | --no-dry-run]
  [--max-results <value>]
  [--next-token <value>]
  --spot-fleet-request-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--max-results`` (integer)


  The maximum number of results to return in a single call. Specify a value between 1 and 1000. The default value is 1000. To retrieve the remaining results, make another call with the returned ``NextToken`` value.

  

``--next-token`` (string)


  The token for the next set of results.

  

``--spot-fleet-request-id`` (string)


  The ID of the Spot fleet request.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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
            "InstanceId": "i-1234567890abcdef0",
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

ActiveInstances -> (list)

  

  The running instances. Note that this list is refreshed periodically and might be out of date.

  

  (structure)

    

    Describes a running instance in a Spot fleet.

    

    InstanceId -> (string)

      

      The ID of the instance.

      

      

    InstanceType -> (string)

      

      The instance type.

      

      

    SpotInstanceRequestId -> (string)

      

      The ID of the Spot instance request.

      

      

    InstanceHealth -> (string)

      

      The health status of the instance. If the status of either the instance status check or the system status check is ``impaired`` , the health status of the instance is ``unhealthy`` . Otherwise, the health status is ``healthy`` .

      

      

    

  

NextToken -> (string)

  

  The token required to retrieve the next set of results. This value is ``null`` when there are no more results to return.

  

  

SpotFleetRequestId -> (string)

  

  The ID of the Spot fleet request.

  

  

