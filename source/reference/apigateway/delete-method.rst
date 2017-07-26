[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway delete-method:


*************
delete-method
*************



===========
Description
===========



Deletes an existing  Method resource.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/apigateway-2015-07-09/DeleteMethod>`_


========
Synopsis
========

::

    delete-method
  --rest-api-id <value>
  --resource-id <value>
  --http-method <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--rest-api-id`` (string)


  The string identifier of the associated  RestApi .

  

``--resource-id`` (string)


  The  Resource identifier for the  Method resource.

  

``--http-method`` (string)


  The HTTP verb of the  Method resource.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To delete a method for the given resource in an API**

Command::

  aws apigateway delete-method --rest-api-id 1234123412 --resource-id a1b2c3 --http-method GET


======
Output
======

None