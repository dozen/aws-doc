[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot list-principal-policies:


***********************
list-principal-policies
***********************



===========
Description
===========



Lists the policies attached to the specified principal. If you use an Amazon Cognito identity, the ID needs to be in `Amazon Cognito Identity format`_ .



========
Synopsis
========

::

    list-principal-policies
  --principal <value>
  [--marker <value>]
  [--page-size <value>]
  [--ascending-order | --no-ascending-order]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--principal`` (string)


  The principal.

  

``--marker`` (string)


  The marker for the next set of results.

  

``--page-size`` (integer)


  The result page size.

  

``--ascending-order`` | ``--no-ascending-order`` (boolean)


  Specifies the order for results. If true, results are returned in ascending creation order.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

policies -> (list)

  

  The policies.

  

  (structure)

    

    Describes an AWS IoT policy.

    

    policyName -> (string)

      

      The policy name.

      

      

    policyArn -> (string)

      

      The policy ARN.

      

      

    

  

nextMarker -> (string)

  

  The marker for the next set of results, or null if there are no additional results.

  

  



.. _Amazon Cognito Identity format: http://docs.aws.amazon.com/cognitoidentity/latest/APIReference/API_GetCredentialsForIdentity.html#API_GetCredentialsForIdentity_RequestSyntax
