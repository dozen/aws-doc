[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway delete-deployment:


*****************
delete-deployment
*****************



===========
Description
===========



Deletes a  Deployment resource. Deleting a deployment will only succeed if there are no  Stage resources associated with it.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/apigateway-2015-07-09/DeleteDeployment>`_


========
Synopsis
========

::

    delete-deployment
  --rest-api-id <value>
  --deployment-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--rest-api-id`` (string)


  The string identifier of the associated  RestApi .

  

``--deployment-id`` (string)


  The identifier of the  Deployment resource to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To delete a deployment in an API**

Command::

  aws apigateway delete-deployment --rest-api-id 1234123412 --deployment-id a1b2c3


======
Output
======

None