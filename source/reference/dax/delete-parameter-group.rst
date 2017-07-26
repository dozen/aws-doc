[ :ref:`aws <cli:aws>` . :ref:`dax <cli:aws dax>` ]

.. _cli:aws dax delete-parameter-group:


**********************
delete-parameter-group
**********************



===========
Description
===========



Deletes the specified parameter group. You cannot delete a parameter group if it is associated with any DAX clusters.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/dax-2017-04-19/DeleteParameterGroup>`_


========
Synopsis
========

::

    delete-parameter-group
  --parameter-group-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--parameter-group-name`` (string)


  The name of the parameter group to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

DeletionMessage -> (string)

  

  A user-specified message for this action (i.e., a reason for deleting the parameter group).

  

  

