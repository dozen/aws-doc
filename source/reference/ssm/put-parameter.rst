[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm put-parameter:


*************
put-parameter
*************



===========
Description
===========



Add one or more parameters to the system.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/PutParameter>`_


========
Synopsis
========

::

    put-parameter
  --name <value>
  [--description <value>]
  --value <value>
  --type <value>
  [--key-id <value>]
  [--overwrite | --no-overwrite]
  [--allowed-pattern <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  The name of the parameter that you want to add to the system.

  

``--description`` (string)


  Information about the parameter that you want to add to the system

  

``--value`` (string)


  The parameter value that you want to add to the system.

  

``--type`` (string)


  The type of parameter that you want to add to the system.

  

  Possible values:

  
  *   ``String``

  
  *   ``StringList``

  
  *   ``SecureString``

  

  

``--key-id`` (string)


  The KMS Key ID that you want to use to encrypt a parameter when you choose the SecureString data type. If you don't specify a key ID, the system uses the default key associated with your AWS account.

  

``--overwrite`` | ``--no-overwrite`` (boolean)


  Overwrite an existing parameter. If not specified, will default to "false".

  

``--allowed-pattern`` (string)


  A regular expression used to validate the parameter value. For example, for String types with values restricted to numbers, you can specify the following: AllowedPattern=^\d+$ 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create a parameter that uses a String data type**

This example creates a parameter. There is no output if the command succeeds.

Command::

  aws ssm put-parameter --name "welcome" --type "String" --value "helloWorld"

**To change a parameter value**

This example changes the value of a parameter. There is no output if the command succeeds.

Command::

  aws ssm put-parameter --name "welcome" --type "String" --value "good day sunshine" --overwrite
  

======
Output
======

