[ :ref:`aws <cli:aws>` . :ref:`waf-regional <cli:aws waf-regional>` ]

.. _cli:aws waf-regional associate-web-acl:


*****************
associate-web-acl
*****************



===========
Description
===========



Associates a web ACL with a resource.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/waf-regional-2016-11-28/AssociateWebACL>`_


========
Synopsis
========

::

    associate-web-acl
  --web-acl-id <value>
  --resource-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--web-acl-id`` (string)


  A unique identifier (ID) for the web ACL.

  

``--resource-arn`` (string)


  The ARN (Amazon Resource Name) of the resource to be protected.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

