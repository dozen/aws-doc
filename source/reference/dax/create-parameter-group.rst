[ :ref:`aws <cli:aws>` . :ref:`dax <cli:aws dax>` ]

.. _cli:aws dax create-parameter-group:


**********************
create-parameter-group
**********************



===========
Description
===========



Creates a new parameter group. A parameter group is a collection of parameters that you apply to all of the nodes in a DAX cluster.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/dax-2017-04-19/CreateParameterGroup>`_


========
Synopsis
========

::

    create-parameter-group
  --parameter-group-name <value>
  [--description <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--parameter-group-name`` (string)


  The name of the parameter group to apply to all of the clusters in this replication group.

  

``--description`` (string)


  A description of the parameter group.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ParameterGroup -> (structure)

  

  Represents the output of a *create-parameter-group* action.

  

  ParameterGroupName -> (string)

    

    The name of the parameter group.

    

    

  Description -> (string)

    

    A description of the parameter group.

    

    

  

