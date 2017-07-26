[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm get-parameters:


**************
get-parameters
**************



===========
Description
===========



Get details of a parameter.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/GetParameters>`_


========
Synopsis
========

::

    get-parameters
  --names <value>
  [--with-decryption | --no-with-decryption]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--names`` (list)


  Names of the parameters for which you want to query information.

  



Syntax::

  "string" "string" ...



``--with-decryption`` | ``--no-with-decryption`` (boolean)


  Return decrypted secure string value. Return decrypted values for secure string parameters. This flag is ignored for String and StringList parameter types.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To list the values for a parameter**

This example lists the values for a parameter.

Command::

  aws ssm get-parameters --names "helloWorld"
  
Output::

  {
	"InvalidParameters": [],
	"Parameters": [
		{
			"Type": "String",
			"Name": "helloWorld",
			"Value": "good day sunshine"
		}
	]
  }


======
Output
======

Parameters -> (list)

  

  A list of details for a parameter.

  

  (structure)

    

    An Amazon EC2 Systems Manager parameter in Parameter Store.

    

    Name -> (string)

      

      The name of the parameter.

      

      

    Type -> (string)

      

      The type of parameter. Valid values include the following: String, String list, Secure string.

      

      

    Value -> (string)

      

      The parameter value.

      

      

    

  

InvalidParameters -> (list)

  

  A list of parameters that are not formatted correctly or do not run when executed.

  

  (string)

    

    

  

