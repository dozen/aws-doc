[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm get-parameter:


*************
get-parameter
*************



===========
Description
===========



Get information about a parameter by using the parameter name. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/GetParameter>`_


========
Synopsis
========

::

    get-parameter
  --name <value>
  [--with-decryption | --no-with-decryption]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  The name of the parameter you want to query.

  

``--with-decryption`` | ``--no-with-decryption`` (boolean)


  Return decrypted values for secure string parameters. This flag is ignored for String and StringList parameter types.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Parameter -> (structure)

  

  Information about a parameter.

  

  Name -> (string)

    

    The name of the parameter.

    

    

  Type -> (string)

    

    The type of parameter. Valid values include the following: String, String list, Secure string.

    

    

  Value -> (string)

    

    The parameter value.

    

    

  

