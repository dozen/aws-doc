[ :ref:`aws <cli:aws>` . :ref:`codecommit <cli:aws codecommit>` ]

.. _cli:aws codecommit test-repository-triggers:


************************
test-repository-triggers
************************



===========
Description
===========



Tests the functionality of repository triggers by sending information to the trigger target. If real data is available in the repository, the test will send data from the last commit. If no data is available, sample data will be generated.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codecommit-2015-04-13/TestRepositoryTriggers>`_


========
Synopsis
========

::

    test-repository-triggers
  --repository-name <value>
  --triggers <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--repository-name`` (string)


  The name of the repository in which to test the triggers.

  

``--triggers`` (list)


  The list of triggers to test.

  



Shorthand Syntax::

    name=string,destinationArn=string,customData=string,branches=string,string,events=string,string ...




JSON Syntax::

  [
    {
      "name": "string",
      "destinationArn": "string",
      "customData": "string",
      "branches": ["string", ...],
      "events": ["all"|"updateReference"|"createReference"|"deleteReference", ...]
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

successfulExecutions -> (list)

  

  The list of triggers that were successfully tested. This list provides the names of the triggers that were successfully tested, separated by commas.

  

  (string)

    

    

  

failedExecutions -> (list)

  

  The list of triggers that were not able to be tested. This list provides the names of the triggers that could not be tested, separated by commas.

  

  (structure)

    

    A trigger failed to run.

    

    trigger -> (string)

      

      The name of the trigger that did not run.

      

      

    failureMessage -> (string)

      

      Additional message information about the trigger that did not run.

      

      

    

  

