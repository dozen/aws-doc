[ :ref:`aws <cli:aws>` . :ref:`elasticbeanstalk <cli:aws elasticbeanstalk>` ]

.. _cli:aws elasticbeanstalk restart-app-server:


******************
restart-app-server
******************



===========
Description
===========



Causes the environment to restart the application container server running on each Amazon EC2 instance. 



========
Synopsis
========

::

    restart-app-server
  [--environment-id <value>]
  [--environment-name <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--environment-id`` (string)


  The ID of the environment to restart the server for. 

   

  Condition: You must specify either this or an EnvironmentName, or both. If you do not specify either, AWS Elastic Beanstalk returns ``MissingRequiredParameter`` error. 

  

``--environment-name`` (string)


  The name of the environment to restart the server for. 

   

  Condition: You must specify either this or an EnvironmentId, or both. If you do not specify either, AWS Elastic Beanstalk returns ``MissingRequiredParameter`` error. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To restart application servers**

The following command restarts application servers on all instances in an environment named ``my-env``::

  aws elasticbeanstalk restart-app-server --environment-name my-env


======
Output
======

None