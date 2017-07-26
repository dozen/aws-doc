[ :ref:`aws <cli:aws>` . :ref:`workdocs <cli:aws workdocs>` ]

.. _cli:aws workdocs describe-notification-subscriptions:


***********************************
describe-notification-subscriptions
***********************************



===========
Description
===========



Lists the specified notification subscriptions.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/workdocs-2016-05-01/DescribeNotificationSubscriptions>`_


========
Synopsis
========

::

    describe-notification-subscriptions
  --organization-id <value>
  [--marker <value>]
  [--limit <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--organization-id`` (string)


  The ID of the organization.

  

``--marker`` (string)


  The marker for the next set of results. (You received this marker from a previous call.)

  

``--limit`` (integer)


  The maximum number of items to return with this call.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Subscriptions -> (list)

  

  The subscriptions.

  

  (structure)

    

    Describes a subscription.

    

    SubscriptionId -> (string)

      

      The ID of the subscription.

      

      

    EndPoint -> (string)

      

      The endpoint of the subscription.

      

      

    Protocol -> (string)

      

      The protocol of the subscription.

      

      

    

  

Marker -> (string)

  

  The marker to use when requesting the next set of results. If there are no additional results, the string is empty.

  

  

