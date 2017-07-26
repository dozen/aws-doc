[ :ref:`aws <cli:aws>` . :ref:`logs <cli:aws logs>` ]

.. _cli:aws logs put-destination-policy:


**********************
put-destination-policy
**********************



===========
Description
===========



Creates or updates an access policy associated with an existing destination. An access policy is an `IAM policy document <http://docs.aws.amazon.com/IAM/latest/UserGuide/policies_overview.html>`_ that is used to authorize claims to register a subscription filter against a given destination.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/logs-2014-03-28/PutDestinationPolicy>`_


========
Synopsis
========

::

    put-destination-policy
  --destination-name <value>
  --access-policy <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--destination-name`` (string)


  A name for an existing destination.

  

``--access-policy`` (string)


  An IAM policy document that authorizes cross-account users to deliver their log events to the associated destination.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None