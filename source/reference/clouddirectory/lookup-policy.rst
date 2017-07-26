[ :ref:`aws <cli:aws>` . :ref:`clouddirectory <cli:aws clouddirectory>` ]

.. _cli:aws clouddirectory lookup-policy:


*************
lookup-policy
*************



===========
Description
===========



Lists all policies from the root of the  Directory to the object specified. If there are no policies present, an empty list is returned. If policies are present, and if some objects don't have the policies attached, it returns the ``ObjectIdentifier`` for such objects. If policies are present, it returns ``ObjectIdentifier`` , ``policyId`` , and ``policyType`` . Paths that don't lead to the root from the target object are ignored. For more information, see `Policies <http://docs.aws.amazon.com/directoryservice/latest/admin-guide/cd_key_concepts.html#policies>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/clouddirectory-2016-05-10/LookupPolicy>`_


========
Synopsis
========

::

    lookup-policy
  --directory-arn <value>
  --object-reference <value>
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--directory-arn`` (string)


  The Amazon Resource Name (ARN) that is associated with the  Directory . For more information, see  arns .

  

``--object-reference`` (structure)


  Reference that identifies the object whose policies will be looked up.

  



Shorthand Syntax::

    Selector=string




JSON Syntax::

  {
    "Selector": "string"
  }



``--next-token`` (string)


  The token to request the next page of results.

  

``--max-results`` (integer)


  The maximum number of items to be retrieved in a single call. This is an approximate number.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

PolicyToPathList -> (list)

  

  Provides list of path to policies. Policies contain ``PolicyId`` , ``ObjectIdentifier`` , and ``PolicyType`` . For more information, see `Policies <http://docs.aws.amazon.com/directoryservice/latest/admin-guide/cd_key_concepts.html#policies>`_ .

  

  (structure)

    

    Used when a regular object exists in a  Directory and you want to find all of the policies that are associated with that object and the parent to that object.

    

    Path -> (string)

      

      The path that is referenced from the root.

      

      

    Policies -> (list)

      

      List of policy objects.

      

      (structure)

        

        Contains the ``PolicyType`` , ``PolicyId`` , and the ``ObjectIdentifier`` to which it is attached. For more information, see `Policies <http://docs.aws.amazon.com/directoryservice/latest/admin-guide/cd_key_concepts.html#policies>`_ .

        

        PolicyId -> (string)

          

          The ID of ``PolicyAttachment`` .

          

          

        ObjectIdentifier -> (string)

          

          The ``ObjectIdentifier`` that is associated with ``PolicyAttachment`` .

          

          

        PolicyType -> (string)

          

          The type of policy that can be associated with ``PolicyAttachment`` .

          

          

        

      

    

  

NextToken -> (string)

  

  The pagination token.

  

  

