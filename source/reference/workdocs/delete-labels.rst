[ :ref:`aws <cli:aws>` . :ref:`workdocs <cli:aws workdocs>` ]

.. _cli:aws workdocs delete-labels:


*************
delete-labels
*************



===========
Description
===========



Deletes the specified list of labels from a resource.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/workdocs-2016-05-01/DeleteLabels>`_


========
Synopsis
========

::

    delete-labels
  --resource-id <value>
  [--authentication-token <value>]
  [--labels <value>]
  [--delete-all | --no-delete-all]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--resource-id`` (string)


  The ID of the resource.

  

``--authentication-token`` (string)


  Amazon WorkDocs authentication token. This field should not be set when using administrative API actions, as in accessing the API using AWS credentials.

  

``--labels`` (list)


  List of labels to delete from the resource.

  



Syntax::

  "string" "string" ...



``--delete-all`` | ``--no-delete-all`` (boolean)


  Flag to request removal of all labels from the specified resource.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

