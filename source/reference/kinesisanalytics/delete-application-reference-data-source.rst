[ :ref:`aws <cli:aws>` . :ref:`kinesisanalytics <cli:aws kinesisanalytics>` ]

.. _cli:aws kinesisanalytics delete-application-reference-data-source:


****************************************
delete-application-reference-data-source
****************************************



===========
Description
===========



Deletes a reference data source configuration from the specified application configuration.

 

If the application is running, Amazon Kinesis Analytics immediately removes the in-application table that you created using the  add-application-reference-data-source operation. 

 

This operation requires permissions to perform the ``kinesisanalytics.DeleteApplicationReferenceDataSource`` action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/kinesisanalytics-2015-08-14/DeleteApplicationReferenceDataSource>`_


========
Synopsis
========

::

    delete-application-reference-data-source
  --application-name <value>
  --current-application-version-id <value>
  --reference-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-name`` (string)


  Name of an existing application.

  

``--current-application-version-id`` (long)


  Version of the application. You can use the  describe-application operation to get the current application version. If the version specified is not the current version, the ``ConcurrentModificationException`` is returned.

  

``--reference-id`` (string)


  ID of the reference data source. When you add a reference data source to your application using the  add-application-reference-data-source , Amazon Kinesis Analytics assigns an ID. You can use the  describe-application operation to get the reference ID. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

