[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm get-parameter-history:


*********************
get-parameter-history
*********************



===========
Description
===========



Query a list of all parameters used by the AWS account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/GetParameterHistory>`_


========
Synopsis
========

::

    get-parameter-history
  --name <value>
  [--with-decryption | --no-with-decryption]
  [--max-results <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  The name of a parameter you want to query.

  

``--with-decryption`` | ``--no-with-decryption`` (boolean)


  Return decrypted values for secure string parameters. This flag is ignored for String and StringList parameter types.

  

``--max-results`` (integer)


  The maximum number of items to return for this call. The call also returns a token that you can specify in a subsequent call to get the next set of results.

  

``--next-token`` (string)


  The token for the next set of items to return. (You received this token from a previous call.)

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To get a value history for a parameter**

This example lists the value history for a parameter.

Command::

  aws ssm get-parameter-history --name "welcome"
  
Output::

  {
    "Parameters": [
        {
            "LastModifiedUser": "arn:aws:iam::812345678901:user/admin",
            "LastModifiedDate": 1487880053.085,
            "Type": "String",
            "Name": "welcome",
            "Value": "helloWorld"
        }
    ]
  }


======
Output
======

Parameters -> (list)

  

  A list of parameters returned by the request.

  

  (structure)

    

    Information about parameter usage.

    

    Name -> (string)

      

      The name of the parameter.

      

      

    Type -> (string)

      

      The type of parameter used.

      

      

    KeyId -> (string)

      

      The ID of the query key used for this parameter.

      

      

    LastModifiedDate -> (timestamp)

      

      Date the parameter was last changed or updated.

      

      

    LastModifiedUser -> (string)

      

      Amazon Resource Name (ARN) of the AWS user who last changed the parameter.

      

      

    Description -> (string)

      

      Information about the parameter.

      

      

    Value -> (string)

      

      The parameter value.

      

      

    AllowedPattern -> (string)

      

      Parameter names can include the following letters and symbols.

       

      a-zA-Z0-9_.-

      

      

    

  

NextToken -> (string)

  

  The token to use when requesting the next set of items. If there are no additional items to return, the string is empty.

  

  

