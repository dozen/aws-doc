[ :ref:`aws <cli:aws>` . :ref:`cloudformation <cli:aws cloudformation>` ]

.. _cli:aws cloudformation list-stack-sets:


***************
list-stack-sets
***************



===========
Description
===========



Returns summary information about stack sets that are associated with the user.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudformation-2010-05-15/ListStackSets>`_


========
Synopsis
========

::

    list-stack-sets
  [--next-token <value>]
  [--max-results <value>]
  [--status <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--next-token`` (string)


  If the previous paginated request didn't return all of the remaining results, the response object's ``next-token`` parameter value is set to a token. To retrieve the next set of results, call ``list-stack-sets`` again and assign that token to the request object's ``next-token`` parameter. If there are no remaining results, the previous response object's ``next-token`` parameter is set to ``null`` .

  

``--max-results`` (integer)


  The maximum number of results to be returned with a single call. If the number of available results exceeds this maximum, the response includes a ``next-token`` value that you can assign to the ``next-token`` request parameter to get the next set of results.

  

``--status`` (string)


  The status of the stack sets that you want to get summary information about.

  

  Possible values:

  
  *   ``ACTIVE``

  
  *   ``DELETED``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Summaries -> (list)

  

  A list of ``StackSetSummary`` structures that contain information about the user's stack sets.

  

  (structure)

    

    The structures that contain summary information about the specified stack set.

    

    StackSetName -> (string)

      

      The name of the stack set.

      

      

    StackSetId -> (string)

      

      The ID of the stack set.

      

      

    Description -> (string)

      

      A description of the stack set that you specify when the stack set is created or updated.

      

      

    Status -> (string)

      

      The status of the stack set.

      

      

    

  

NextToken -> (string)

  

  If the request doesn't return all of the remaining results, ``next-token`` is set to a token. To retrieve the next set of results, call ``list-stack-instances`` again and assign that token to the request object's ``next-token`` parameter. If the request returns all results, ``next-token`` is set to ``null`` .

  

  

