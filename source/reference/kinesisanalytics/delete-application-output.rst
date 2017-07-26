[ :ref:`aws <cli:aws>` . :ref:`kinesisanalytics <cli:aws kinesisanalytics>` ]

.. _cli:aws kinesisanalytics delete-application-output:


*************************
delete-application-output
*************************



===========
Description
===========



Deletes output destination configuration from your application configuration. Amazon Kinesis Analytics will no longer write data from the corresponding in-application stream to the external output destination.

 

This operation requires permissions to perform the ``kinesisanalytics:DeleteApplicationOutput`` action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/kinesisanalytics-2015-08-14/DeleteApplicationOutput>`_


========
Synopsis
========

::

    delete-application-output
  --application-name <value>
  --current-application-version-id <value>
  --output-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-name`` (string)


  Amazon Kinesis Analytics application name.

  

``--current-application-version-id`` (long)


  Amazon Kinesis Analytics application version. You can use the  describe-application operation to get the current application version. If the version specified is not the current version, the ``ConcurrentModificationException`` is returned. 

  

``--output-id`` (string)


  The ID of the configuration to delete. Each output configuration that is added to the application, either when the application is created or later using the  add-application-output operation, has a unique ID. You need to provide the ID to uniquely identify the output configuration that you want to delete from the application configuration. You can use the  describe-application operation to get the specific ``OutputId`` . 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

