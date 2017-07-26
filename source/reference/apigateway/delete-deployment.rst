[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway delete-deployment:


*****************
delete-deployment
*****************



===========
Description
===========



Deletes a  Deployment resource. Deleting a deployment will only succeed if there are no  Stage resources associated with it.



========
Synopsis
========

::

    delete-deployment
  --rest-api-id <value>
  --deployment-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--rest-api-id`` (string)


  The identifier of the  RestApi resource for the  Deployment resource to delete.

  

``--deployment-id`` (string)


  The identifier of the  Deployment resource to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None