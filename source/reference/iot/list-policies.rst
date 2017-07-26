[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot list-policies:


*************
list-policies
*************



===========
Description
===========



Lists your policies.



========
Synopsis
========

::

    list-policies
  [--marker <value>]
  [--page-size <value>]
  [--ascending-order | --no-ascending-order]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--marker`` (string)


  The marker for the next set of results.

  

``--page-size`` (integer)


  The result page size.

  

``--ascending-order`` | ``--no-ascending-order`` (boolean)


  Specifies the order for results. If true, the results are returned in ascending creation order.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

policies -> (list)

  

  The descriptions of the policies.

  

  (structure)

    

    Describes an AWS IoT policy.

    

    policyName -> (string)

      

      The policy name.

      

      

    policyArn -> (string)

      

      The policy ARN.

      

      

    

  

nextMarker -> (string)

  

  The marker for the next set of results, or null if there are no additional results.

  

  

