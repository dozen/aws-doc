[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 modify-vpc-endpoint:


*******************
modify-vpc-endpoint
*******************



===========
Description
===========



Modifies attributes of a specified VPC endpoint. You can modify the policy associated with the endpoint, and you can add and remove route tables associated with the endpoint.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/ModifyVpcEndpoint>`_


========
Synopsis
========

::

    modify-vpc-endpoint
  [--add-route-table-ids <value>]
  [--dry-run | --no-dry-run]
  [--policy-document <value>]
  [--remove-route-table-ids <value>]
  [--reset-policy | --no-reset-policy]
  --vpc-endpoint-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--add-route-table-ids`` (list)


  One or more route tables IDs to associate with the endpoint.

  



Syntax::

  "string" "string" ...



``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--policy-document`` (string)


  A policy document to attach to the endpoint. The policy must be in valid JSON format.

  

``--remove-route-table-ids`` (list)


  One or more route table IDs to disassociate from the endpoint.

  



Syntax::

  "string" "string" ...



``--reset-policy`` | ``--no-reset-policy`` (boolean)


  Specify ``true`` to reset the policy document to the default policy. The default policy allows access to the service.

  

``--vpc-endpoint-id`` (string)


  The ID of the endpoint.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To modify an endpoint**

This example modifies endpoint vpce-1a2b3c4d by associating route table rtb-aaa222bb with the endpoint, and resetting the policy document.

Command::

  aws ec2 modify-vpc-endpoint --vpc-endpoint-id vpce-1a2b3c4d --add-route-table-ids rtb-aaa222bb --reset-policy

Output::

  {
    "Return": true
  }

======
Output
======

Return -> (boolean)

  

  Returns ``true`` if the request succeeds; otherwise, it returns an error.

  

  

