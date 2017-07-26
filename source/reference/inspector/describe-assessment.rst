[ :ref:`aws <cli:aws>` . :ref:`inspector <cli:aws inspector>` ]

.. _cli:aws inspector describe-assessment:


*******************
describe-assessment
*******************



===========
Description
===========



Describes the assessment specified by the assessment ARN.



========
Synopsis
========

::

    describe-assessment
  --assessment-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--assessment-arn`` (string)


  The ARN specifying the assessment that you want to describe.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

assessment -> (structure)

  

  Information about the assessment.

  

  assessmentArn -> (string)

    

    The ARN of the assessment.

    

    

  assessmentName -> (string)

    

    The name of the assessment.

    

    

  applicationArn -> (string)

    

    The ARN of the application that corresponds to this assessment.

    

    

  assessmentState -> (string)

    

    The state of the assessment. Values can be set to *Created* , *Collecting Data* , *Stopping* , and *Completed* .

    

    

  failureMessage -> (string)

    

    This data type property is not currently used.

    

    

  dataCollected -> (boolean)

    

    Boolean value (true or false) specifying whether the data collection process is completed.

    

    

  startTime -> (timestamp)

    

    The assessment start time.

    

    

  endTime -> (timestamp)

    

    The assessment end time.

    

    

  durationInSeconds -> (integer)

    

    The assessment duration in seconds. The default value is 3600 seconds (one hour). The maximum value is 86400 seconds (one day).

    

    

  userAttributesForFindings -> (list)

    

    The user-defined attributes that are assigned to every generated finding.

    

    (structure)

      

      This data type is used as a response element in the  add-attributes-to-findings action and a request parameter in the  create-assessment action.

      

      key -> (string)

        

        The attribute key.

        

        

      value -> (string)

        

        The value assigned to the attribute key.

        

        

      

    

  

