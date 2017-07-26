[ :ref:`aws <cli:aws>` . :ref:`support <cli:aws support>` ]

.. _cli:aws support describe-trusted-advisor-checks:


*******************************
describe-trusted-advisor-checks
*******************************



===========
Description
===========



Returns information about all available Trusted Advisor checks, including name, ID, category, description, and metadata. You must specify a language code; English ("en") and Japanese ("ja") are currently supported. The response contains a  TrustedAdvisorCheckDescription for each check.



========
Synopsis
========

::

    describe-trusted-advisor-checks
  --language <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--language`` (string)


  The ISO 639-1 code for the language in which AWS provides support. AWS Support currently supports English ("en") and Japanese ("ja"). Language parameters must be passed explicitly for operations that take them.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

checks -> (list)

  

  Information about all available Trusted Advisor checks.

  

  (structure)

    

    The description and metadata for a Trusted Advisor check.

    

    id -> (string)

      

      The unique identifier for the Trusted Advisor check.

      

      

    name -> (string)

      

      The display name for the Trusted Advisor check.

      

      

    description -> (string)

      

      The description of the Trusted Advisor check, which includes the alert criteria and recommended actions (contains HTML markup).

      

      

    category -> (string)

      

      The category of the Trusted Advisor check.

      

      

    metadata -> (list)

      

      The column headings for the data returned by the Trusted Advisor check. The order of the headings corresponds to the order of the data in the **Metadata** element of the  TrustedAdvisorResourceDetail for the check. **Metadata** contains all the data that is shown in the Excel download, even in those cases where the UI shows just summary data. 

      

      (string)

        

        

      

    

  

