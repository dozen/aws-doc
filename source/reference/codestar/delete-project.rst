[ :ref:`aws <cli:aws>` . :ref:`codestar <cli:aws codestar>` ]

.. _cli:aws codestar delete-project:


**************
delete-project
**************



===========
Description
===========



Deletes a project, including project resources. Does not delete users associated with the project, but does delete the IAM roles that allowed access to the project.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codestar-2017-04-19/DeleteProject>`_


========
Synopsis
========

::

    delete-project
  --id <value>
  [--client-request-token <value>]
  [--delete-stack | --no-delete-stack]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--id`` (string)


  The ID of the project to be deleted in AWS CodeStar.

  

``--client-request-token`` (string)


  A user- or system-generated token that identifies the entity that requested project deletion. This token can be used to repeat the request. 

  

``--delete-stack`` | ``--no-delete-stack`` (boolean)


  Whether to send a delete request for the primary stack in AWS CloudFormation originally used to generate the project and its resources. This option will delete all AWS resources for the project (except for any buckets in Amazon S3) as well as deleting the project itself. Recommended for most use cases.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

stackId -> (string)

  

  The ID of the primary stack in AWS CloudFormation that will be deleted as part of deleting the project and its resources.

  

  

projectArn -> (string)

  

  The Amazon Resource Name (ARN) of the deleted project.

  

  

