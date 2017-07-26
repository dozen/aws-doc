[ :ref:`aws <cli:aws>` . :ref:`elasticbeanstalk <cli:aws elasticbeanstalk>` ]

.. _cli:aws elasticbeanstalk delete-application:


******************
delete-application
******************



===========
Description
===========



Deletes the specified application along with all associated versions and configurations. The application versions will not be deleted from your Amazon S3 bucket.

 

.. note::

   

  You cannot delete an application that has a running environment.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticbeanstalk-2010-12-01/DeleteApplication>`_


========
Synopsis
========

::

    delete-application
  --application-name <value>
  [--terminate-env-by-force | --no-terminate-env-by-force]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-name`` (string)


  The name of the application to delete.

  

``--terminate-env-by-force`` | ``--no-terminate-env-by-force`` (boolean)


  When set to true, running environments will be terminated before deleting the application.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To delete an application**

The following command deletes an application named ``my-app``::

  aws elasticbeanstalk delete-application --application-name my-app


======
Output
======

None