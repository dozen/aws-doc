[ :ref:`aws <cli:aws>` . :ref:`elasticbeanstalk <cli:aws elasticbeanstalk>` ]

.. _cli:aws elasticbeanstalk delete-application-version:


**************************
delete-application-version
**************************



===========
Description
===========



Deletes the specified version from the specified application.

 

.. note::

   

  You cannot delete an application version that is associated with a running environment.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticbeanstalk-2010-12-01/DeleteApplicationVersion>`_


========
Synopsis
========

::

    delete-application-version
  --application-name <value>
  --version-label <value>
  [--delete-source-bundle | --no-delete-source-bundle]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-name`` (string)


  The name of the application to which the version belongs.

  

``--version-label`` (string)


  The label of the version to delete.

  

``--delete-source-bundle`` | ``--no-delete-source-bundle`` (boolean)


  Set to ``true`` to delete the source bundle from your storage bucket. Otherwise, the application version is deleted only from Elastic Beanstalk and the source bundle remains in Amazon S3.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To delete an application version**

The following command deletes an application version named ``22a0-stage-150819_182129`` for an application named ``my-app``::

  aws elasticbeanstalk delete-application-version --version-label 22a0-stage-150819_182129 --application-name my-app


======
Output
======

None