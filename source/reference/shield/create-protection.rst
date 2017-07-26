[ :ref:`aws <cli:aws>` . :ref:`shield <cli:aws shield>` ]

.. _cli:aws shield create-protection:


*****************
create-protection
*****************



===========
Description
===========



Enables AWS Shield Advanced for a specific AWS resource. The resource can be an Amazon CloudFront distribution, Elastic Load Balancing load balancer, or an Amazon Route 53 hosted zone.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/shield-2016-06-02/CreateProtection>`_


========
Synopsis
========

::

    create-protection
  --name <value>
  --resource-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  Friendly name for the ``Protection`` you are creating.

  

``--resource-arn`` (string)


  The ARN (Amazon Resource Name) of the resource to be protected.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ProtectionId -> (string)

  

  The unique identifier (ID) for the  Protection object that is created.

  

  

