[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy create-deployment-config:


************************
create-deployment-config
************************



===========
Description
===========



Creates a new deployment configuration.



========
Synopsis
========

::

    create-deployment-config
  --deployment-config-name <value>
  [--minimum-healthy-hosts <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--deployment-config-name`` (string)


  The name of the deployment configuration to create.

  

``--minimum-healthy-hosts`` (structure)


  The minimum number of healthy instances that should be available at any time during the deployment. There are two parameters expected in the input: type and value.

   

  The type parameter takes either of the following values:

   

   
  * HOST_COUNT: The value parameter represents the minimum number of healthy instances, as an absolute value.
   
  * FLEET_PERCENT: The value parameter represents the minimum number of healthy instances, as a percentage of the total number of instances in the deployment. If you specify FLEET_PERCENT, then at the start of the deployment AWS CodeDeploy converts the percentage to the equivalent number of instances and rounds fractional instances up.
   

   

  The value parameter takes an integer.

   

  For example, to set a minimum of 95% healthy instances, specify a type of FLEET_PERCENT and a value of 95.

  



Shorthand Syntax::

    value=integer,type=string




JSON Syntax::

  {
    "value": integer,
    "type": "HOST_COUNT"|"FLEET_PERCENT"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To create a custom deployment configuration**

This example creates a custom deployment configuration and associates it with the user's AWS account.

Command::

  aws deploy create-deployment-config --deployment-config-name ThreeQuartersHealthy --minimum-healthy-hosts type=FLEET_PERCENT,value=75

Output::

  {
      "deploymentConfigId": "bf6b390b-61d3-4f24-8911-a1664EXAMPLE"
  }

======
Output
======

deploymentConfigId -> (string)

  

  A unique deployment configuration ID.

  

  

