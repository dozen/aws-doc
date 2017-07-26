[ :ref:`aws <cli:aws>` . :ref:`elasticbeanstalk <cli:aws elasticbeanstalk>` ]

.. _cli:aws elasticbeanstalk rebuild-environment:


*******************
rebuild-environment
*******************



===========
Description
===========



Deletes and recreates all of the AWS resources (for example: the Auto Scaling group, load balancer, etc.) for a specified environment and forces a restart. 



========
Synopsis
========

::

    rebuild-environment
  [--environment-id <value>]
  [--environment-name <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--environment-id`` (string)


  The ID of the environment to rebuild. 

   

  Condition: You must specify either this or an EnvironmentName, or both. If you do not specify either, AWS Elastic Beanstalk returns ``MissingRequiredParameter`` error. 

  

``--environment-name`` (string)


  The name of the environment to rebuild. 

   

  Condition: You must specify either this or an EnvironmentId, or both. If you do not specify either, AWS Elastic Beanstalk returns ``MissingRequiredParameter`` error. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To rebuild an environment**

The following command terminates and recreates the resources in an environment named ``my-env``::

  aws elasticbeanstalk rebuild-environment --environment-name my-env


======
Output
======

None