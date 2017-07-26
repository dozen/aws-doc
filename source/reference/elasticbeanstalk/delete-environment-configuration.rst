[ :ref:`aws <cli:aws>` . :ref:`elasticbeanstalk <cli:aws elasticbeanstalk>` ]

.. _cli:aws elasticbeanstalk delete-environment-configuration:


********************************
delete-environment-configuration
********************************



===========
Description
===========



Deletes the draft configuration associated with the running environment. 

 

Updating a running environment with any configuration changes creates a draft configuration set. You can get the draft configuration using  describe-configuration-settings while the update is in progress or if the update fails. The ``DeploymentStatus`` for the draft configuration indicates whether the deployment is in process or has failed. The draft configuration remains in existence until it is deleted with this action. 



========
Synopsis
========

::

    delete-environment-configuration
  --application-name <value>
  --environment-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--application-name`` (string)


  The name of the application the environment is associated with. 

  

``--environment-name`` (string)


  The name of the environment to delete the draft configuration from. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To delete a draft configuration**

The following command deletes a draft configuration for an environment named ``my-env``::

  aws elasticbeanstalk delete-environment-configuration --environment-name my-env --application-name my-app


======
Output
======

None