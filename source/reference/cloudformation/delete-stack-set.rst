[ :ref:`aws <cli:aws>` . :ref:`cloudformation <cli:aws cloudformation>` ]

.. _cli:aws cloudformation delete-stack-set:


****************
delete-stack-set
****************



===========
Description
===========



Deletes a stack set. Before you can delete a stack set, all of its member stack instances must be deleted. For more information about how to do this, see  delete-stack-instances . 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudformation-2010-05-15/DeleteStackSet>`_


========
Synopsis
========

::

    delete-stack-set
  --stack-set-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--stack-set-name`` (string)


  The name or unique ID of the stack set that you're deleting. You can obtain this value by running  list-stack-sets .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

