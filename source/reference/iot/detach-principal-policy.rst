[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot detach-principal-policy:


***********************
detach-principal-policy
***********************



===========
Description
===========



Removes the specified policy from the specified certificate.



========
Synopsis
========

::

    detach-principal-policy
  --policy-name <value>
  --principal <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--policy-name`` (string)


  The name of the policy to detach.

  

``--principal`` (string)


  The principal

   

  If the principal is a certificate, specify the certificate ARN. If the principal is a Cognito identity specify the identity ID.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None