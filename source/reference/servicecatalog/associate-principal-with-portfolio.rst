[ :ref:`aws <cli:aws>` . :ref:`servicecatalog <cli:aws servicecatalog>` ]

.. _cli:aws servicecatalog associate-principal-with-portfolio:


**********************************
associate-principal-with-portfolio
**********************************



===========
Description
===========



Associates the specified principal ARN with the specified portfolio.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/servicecatalog-2015-12-10/AssociatePrincipalWithPortfolio>`_


========
Synopsis
========

::

    associate-principal-with-portfolio
  [--accept-language <value>]
  --portfolio-id <value>
  --principal-arn <value>
  --principal-type <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--accept-language`` (string)


  The language code to use for this operation. Supported language codes are as follows:

   

  "en" (English)

   

  "jp" (Japanese)

   

  "zh" (Chinese)

   

  If no code is specified, "en" is used as the default.

  

``--portfolio-id`` (string)


  The portfolio identifier.

  

``--principal-arn`` (string)


  The ARN representing the principal (IAM user, role, or group).

  

``--principal-type`` (string)


  The principal type. Must be ``IAM``  

  

  Possible values:

  
  *   ``IAM``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

