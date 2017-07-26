[ :ref:`aws <cli:aws>` . :ref:`waf-regional <cli:aws waf-regional>` ]

.. _cli:aws waf-regional get-web-acl-for-resource:


************************
get-web-acl-for-resource
************************



===========
Description
===========



Returns the web ACL for the specified resource.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/waf-regional-2016-11-28/GetWebACLForResource>`_


========
Synopsis
========

::

    get-web-acl-for-resource
  --resource-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--resource-arn`` (string)


  The ARN (Amazon Resource Name) of the resource for which to get the web ACL.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

WebACLSummary -> (structure)

  

  Information about the web ACL that you specified in the ``get-web-acl-for-resource`` request. If there is no associated resource, a null WebACLSummary is returned.

  

  WebACLId -> (string)

    

    A unique identifier for a ``WebACL`` . You use ``WebACLId`` to get information about a ``WebACL`` (see  get-web-acl ), update a ``WebACL`` (see  update-web-acl ), and delete a ``WebACL`` from AWS WAF (see  delete-web-acl ).

     

     ``WebACLId`` is returned by  create-web-acl and by  list-web-acls .

    

    

  Name -> (string)

    

    A friendly name or description of the  WebACL . You can't change the name of a ``WebACL`` after you create it.

    

    

  

