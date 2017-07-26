[ :ref:`aws <cli:aws>` . :ref:`codestar <cli:aws codestar>` ]

.. _cli:aws codestar describe-project:


****************
describe-project
****************



===========
Description
===========



Describes a project and its resources.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codestar-2017-04-19/DescribeProject>`_


========
Synopsis
========

::

    describe-project
  --id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--id`` (string)


  The ID of the project.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

name -> (string)

  

  The display name for the project.

  

  

id -> (string)

  

  The ID of the project.

  

  

arn -> (string)

  

  The Amazon Resource Name (ARN) for the project.

  

  

description -> (string)

  

  The description of the project, if any.

  

  

clientRequestToken -> (string)

  

  A user- or system-generated token that identifies the entity that requested project creation. 

  

  

createdTimeStamp -> (timestamp)

  

  The date and time the project was created, in timestamp format.

  

  

stackId -> (string)

  

  The ID of the primary stack in AWS CloudFormation used to generate resources for the project.

  

  

projectTemplateId -> (string)

  

  The ID for the AWS CodeStar project template used to create the project.

  

  

