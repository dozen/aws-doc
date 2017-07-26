[ :ref:`aws <cli:aws>` . :ref:`elasticbeanstalk <cli:aws elasticbeanstalk>` ]

.. _cli:aws elasticbeanstalk restart-app-server:


******************
restart-app-server
******************



===========
Description
===========



Causes the environment to restart the application container server running on each Amazon EC2 instance.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticbeanstalk-2010-12-01/RestartAppServer>`_


========
Synopsis
========

::

    restart-app-server
  [--environment-id <value>]
  [--environment-name <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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