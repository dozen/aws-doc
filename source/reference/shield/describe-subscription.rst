[ :ref:`aws <cli:aws>` . :ref:`shield <cli:aws shield>` ]

.. _cli:aws shield describe-subscription:


*********************
describe-subscription
*********************



===========
Description
===========



Provides details about the AWS Shield Advanced subscription for an account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/shield-2016-06-02/DescribeSubscription>`_


========
Synopsis
========

::

    describe-subscription
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Subscription -> (structure)

  

  The AWS Shield Advanced subscription details for an account.

  

  StartTime -> (timestamp)

    

    The start time of the subscription, in the format "2016-12-16T13:50Z".

    

    

  TimeCommitmentInSeconds -> (long)

    

    The length, in seconds, of the AWS Shield Advanced subscription for the account.

    

    

  

