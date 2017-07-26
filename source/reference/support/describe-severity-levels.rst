[ :ref:`aws <cli:aws>` . :ref:`support <cli:aws support>` ]

.. _cli:aws support describe-severity-levels:


************************
describe-severity-levels
************************



===========
Description
===========



Returns the list of severity levels that you can assign to an AWS Support case. The severity level for a case is also a field in the  CaseDetails data type included in any  create-case request. 



========
Synopsis
========

::

    describe-severity-levels
  [--language <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--language`` (string)


  The ISO 639-1 code for the language in which AWS provides support. AWS Support currently supports English ("en") and Japanese ("ja"). language parameters must be passed explicitly for operations that take them.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

severityLevels -> (list)

  

  The available severity levels for the support case. Available severity levels are defined by your service level agreement with AWS.

  

  (structure)

    

    A code and name pair that represent a severity level that can be applied to a support case. 

    

    code -> (string)

      

      One of four values: "low," "medium," "high," and "urgent". These values correspond to response times returned to the caller in ``SeverityLevel.name`` . 

      

      

    name -> (string)

      

      The name of the severity level that corresponds to the severity level code.

      

      

    

  

