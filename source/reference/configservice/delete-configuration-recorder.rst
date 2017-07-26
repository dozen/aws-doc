[ :ref:`aws <cli:aws>` . :ref:`configservice <cli:aws configservice>` ]

.. _cli:aws configservice delete-configuration-recorder:


*****************************
delete-configuration-recorder
*****************************



===========
Description
===========



Deletes the configuration recorder.

 

After the configuration recorder is deleted, AWS Config will not record resource configuration changes until you create a new configuration recorder.

 

This action does not delete the configuration information that was previously recorded. You will be able to access the previously recorded information by using the ``get-resource-config-history`` action, but you will not be able to access this information in the AWS Config console until you create a new configuration recorder.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/config-2014-11-12/DeleteConfigurationRecorder>`_


========
Synopsis
========

::

    delete-configuration-recorder
  --configuration-recorder-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--configuration-recorder-name`` (string)


  The name of the configuration recorder to be deleted. You can retrieve the name of your configuration recorder by using the ``describe-configuration-recorders`` action.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None