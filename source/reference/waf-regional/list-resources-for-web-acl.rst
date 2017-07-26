[ :ref:`aws <cli:aws>` . :ref:`waf-regional <cli:aws waf-regional>` ]

.. _cli:aws waf-regional list-resources-for-web-acl:


**************************
list-resources-for-web-acl
**************************



===========
Description
===========



Returns an array of resources associated with the specified web ACL.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/waf-regional-2016-11-28/ListResourcesForWebACL>`_


========
Synopsis
========

::

    list-resources-for-web-acl
  --web-acl-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--web-acl-id`` (string)


  The unique identifier (ID) of the web ACL for which to list the associated resources.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ResourceArns -> (list)

  

  An array of ARNs (Amazon Resource Names) of the resources associated with the specified web ACL. An array with zero elements is returned if there are no resources associated with the web ACL.

  

  (string)

    

    

  

