[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 accept-reserved-instances-exchange-quote:


****************************************
accept-reserved-instances-exchange-quote
****************************************



===========
Description
===========



Accepts the Convertible Reserved Instance exchange quote described in the  get-reserved-instances-exchange-quote call.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/AcceptReservedInstancesExchangeQuote>`_


========
Synopsis
========

::

    accept-reserved-instances-exchange-quote
  [--dry-run | --no-dry-run]
  --reserved-instance-ids <value>
  [--target-configurations <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--reserved-instance-ids`` (list)


  The IDs of the Convertible Reserved Instances to exchange for other Convertible Reserved Instances of the same or higher value.

  



Syntax::

  "string" "string" ...



``--target-configurations`` (list)


  The configurations of the Convertible Reserved Instance offerings that you are purchasing in this exchange.

  



Shorthand Syntax::

    InstanceCount=integer,OfferingId=string ...




JSON Syntax::

  [
    {
      "InstanceCount": integer,
      "OfferingId": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ExchangeId -> (string)

  

  The ID of the successful exchange.

  

  

