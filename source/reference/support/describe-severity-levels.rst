[ :ref:`aws <cli:aws>` . :ref:`support <cli:aws support>` ]

.. _cli:aws support describe-severity-levels:


************************
describe-severity-levels
************************



===========
Description
===========



Returns the list of severity levels that you can assign to an AWS Support case. The severity level for a case is also a field in the  CaseDetails data type included in any  create-case request. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/support-2013-04-15/DescribeSeverityLevels>`_


========
Synopsis
========

::

    describe-severity-levels
  [--language <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--language`` (string)


  The ISO 639-1 code for the language in which AWS provides support. AWS Support currently supports English ("en") and Japanese ("ja"). language parameters must be passed explicitly for operations that take them.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

severityLevels -> (list)

  

  The available severity levels for the support case. Available severity levels are defined by your service level agreement with AWS.

  

  (structure)

    

    A code and name pair that represent a severity level that can be applied to a support case.

    

    code -> (string)

      

      One of four values: "low," "medium," "high," and "urgent". These values correspond to response times returned to the caller in ``severityLevel.name`` . 

      

      

    name -> (string)

      

      The name of the severity level that corresponds to the severity level code.

      

      

    

  

