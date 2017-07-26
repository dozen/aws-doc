[ :ref:`aws <cli:aws>` . :ref:`dax <cli:aws dax>` ]

.. _cli:aws dax update-parameter-group:


**********************
update-parameter-group
**********************



===========
Description
===========



Modifies the parameters of a parameter group. You can modify up to 20 parameters in a single request by submitting a list parameter name and value pairs.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/dax-2017-04-19/UpdateParameterGroup>`_


========
Synopsis
========

::

    update-parameter-group
  --parameter-group-name <value>
  --parameter-name-values <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--parameter-group-name`` (string)


  The name of the parameter group.

  

``--parameter-name-values`` (list)


  An array of name-value pairs for the parameters in the group. Each element in the array represents a single parameter.

  



Shorthand Syntax::

    ParameterName=string,ParameterValue=string ...




JSON Syntax::

  [
    {
      "ParameterName": "string",
      "ParameterValue": "string"
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

ParameterGroup -> (structure)

  

  The parameter group that has been modified.

  

  ParameterGroupName -> (string)

    

    The name of the parameter group.

    

    

  Description -> (string)

    

    A description of the parameter group.

    

    

  

