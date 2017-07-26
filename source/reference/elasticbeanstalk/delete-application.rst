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



========
Synopsis
========

::

    delete-application
  --application-name <value>
  [--terminate-env-by-force | --no-terminate-env-by-force]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--application-name`` (string)


  The name of the application to delete.

  

``--terminate-env-by-force`` | ``--no-terminate-env-by-force`` (boolean)


  When set to true, running environments will be terminated before deleting the application.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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