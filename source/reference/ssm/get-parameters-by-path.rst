[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm get-parameters-by-path:


**********************
get-parameters-by-path
**********************



===========
Description
===========



Retrieve parameters in a specific hierarchy. For more information, see `Working with Systems Manager Parameters <http://docs.aws.amazon.com/systems-manager/latest/userguide/sysman-paramstore-working.html>`_ . 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/GetParametersByPath>`_


========
Synopsis
========

::

    get-parameters-by-path
  --path <value>
  [--recursive | --no-recursive]
  [--parameter-filters <value>]
  [--with-decryption | --no-with-decryption]
  [--max-results <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--path`` (string)


  The hierarchy for the parameter. Hierarchies start with a forward slash (/) and end with the parameter name. A hierarchy can have a maximum of five levels. Examples: /Environment/Test/DBString003

   

  /Finance/Prod/IAD/OS/WinServ2016/license15

  

``--recursive`` | ``--no-recursive`` (boolean)


  Retrieve all parameters within a hierarchy.

  

``--parameter-filters`` (list)


  Filters to limit the request results.

  



Shorthand Syntax::

    Key=string,Option=string,Values=string,string ...




JSON Syntax::

  [
    {
      "Key": "string",
      "Option": "string",
      "Values": ["string", ...]
    }
    ...
  ]



``--with-decryption`` | ``--no-with-decryption`` (boolean)


  Retrieve all parameters in a hierarchy with their value decrypted.

  

``--max-results`` (integer)


  The maximum number of items to return for this call. The call also returns a token that you can specify in a subsequent call to get the next set of results.

  

``--next-token`` (string)


  A token to start the list. Use this token to get the next set of results. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Parameters -> (list)

  

  A list of parameters found in the specified hierarchy.

  

  (structure)

    

    An Amazon EC2 Systems Manager parameter in Parameter Store.

    

    Name -> (string)

      

      The name of the parameter.

      

      

    Type -> (string)

      

      The type of parameter. Valid values include the following: String, String list, Secure string.

      

      

    Value -> (string)

      

      The parameter value.

      

      

    

  

NextToken -> (string)

  

  The token for the next set of items to return. Use this token to get the next set of results.

  

  

