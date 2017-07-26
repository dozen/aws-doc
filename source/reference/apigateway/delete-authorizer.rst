[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway delete-authorizer:


*****************
delete-authorizer
*****************



===========
Description
===========



Deletes an existing  Authorizer resource.

 `AWS CLI <http://docs.aws.amazon.com/cli/latest/reference/apigateway/delete-authorizer.html>`_ 

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/apigateway-2015-07-09/DeleteAuthorizer>`_


========
Synopsis
========

::

    delete-authorizer
  --rest-api-id <value>
  --authorizer-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--rest-api-id`` (string)


  The string identifier of the associated  RestApi .

  

``--authorizer-id`` (string)


  The identifier of the  Authorizer resource.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To delete a Custom Authorizer in an API**

Command::

  aws apigateway delete-authorizer --rest-api-id 1234123412 --authorizer-id 7gkfbo


======
Output
======

None