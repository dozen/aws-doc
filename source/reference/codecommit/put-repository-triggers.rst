[ :ref:`aws <cli:aws>` . :ref:`codecommit <cli:aws codecommit>` ]

.. _cli:aws codecommit put-repository-triggers:


***********************
put-repository-triggers
***********************



===========
Description
===========



Replaces all triggers for a repository. This can be used to create or delete triggers.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codecommit-2015-04-13/PutRepositoryTriggers>`_


========
Synopsis
========

::

    put-repository-triggers
  --repository-name <value>
  --triggers <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--repository-name`` (string)


  The name of the repository where you want to create or update the trigger.

  

``--triggers`` (list)


  The JSON block of configuration information for each trigger.

  



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

configurationId -> (string)

  

  The system-generated unique ID for the create or update operation.

  

  

