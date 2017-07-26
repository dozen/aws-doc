[ :ref:`aws <cli:aws>` . :ref:`waf <cli:aws waf>` ]

.. _cli:aws waf list-web-acls:


*************
list-web-acls
*************



===========
Description
===========



Returns an array of  WebACLSummary objects in the response.



========
Synopsis
========

::

    list-web-acls
  [--next-marker <value>]
  --limit <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--next-marker`` (string)


  If you specify a value for ``Limit`` and you have more ``WebACL`` objects than the number that you specify for ``Limit`` , AWS WAF returns a ``next-marker`` value in the response that allows you to list another group of ``WebACL`` objects. For the second and subsequent ``list-web-acls`` requests, specify the value of ``next-marker`` from the previous response to get information about another batch of ``WebACL`` objects.

  

``--limit`` (integer)


  Specifies the number of ``WebACL`` objects that you want AWS WAF to return for this request. If you have more ``WebACL`` objects than the number that you specify for ``Limit`` , the response includes a ``next-marker`` value that you can use to get another batch of ``WebACL`` objects.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

NextMarker -> (string)

  

  If you have more ``WebACL`` objects than the number that you specified for ``Limit`` in the request, the response includes a ``next-marker`` value. To list more ``WebACL`` objects, submit another ``list-web-acls`` request, and specify the ``next-marker`` value from the response in the ``next-marker`` value in the next request.

  

  

WebACLs -> (list)

  

  An array of  WebACLSummary objects.

  

  (structure)

    

    Contains the identifier and the name or description of the  WebACL .

    

    WebACLId -> (string)

      

      A unique identifier for a ``WebACL`` . You use ``WebACLId`` to get information about a ``WebACL`` (see  get-web-acl ), update a ``WebACL`` (see  update-web-acl , and delete a ``WebACL`` from AWS WAF (see  delete-web-acl ).

       

      ``WebACLId`` is returned by  create-web-acl and by  list-web-acls .

      

      

    Name -> (string)

      

      A friendly name or description of the  WebACL . You can't change the name of a ``WebACL`` after you create it.

      

      

    

  

