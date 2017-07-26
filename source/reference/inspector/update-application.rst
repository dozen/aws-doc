[ :ref:`aws <cli:aws>` . :ref:`inspector <cli:aws inspector>` ]

.. _cli:aws inspector update-application:


******************
update-application
******************



===========
Description
===========



Updates application specified by the application ARN.



========
Synopsis
========

::

    update-application
  --application-arn <value>
  --application-name <value>
  --resource-group-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--application-arn`` (string)


  Application ARN that you want to update.

  

``--application-name`` (string)


  Application name that you want to update.

  

``--resource-group-arn`` (string)


  The resource group ARN that you want to update.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

message -> (string)

  

  Confirmation details of the action performed.

  

  

