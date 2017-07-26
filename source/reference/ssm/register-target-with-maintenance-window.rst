[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm register-target-with-maintenance-window:


***************************************
register-target-with-maintenance-window
***************************************



===========
Description
===========



Registers a target with a Maintenance Window.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/RegisterTargetWithMaintenanceWindow>`_


========
Synopsis
========

::

    register-target-with-maintenance-window
  --window-id <value>
  --resource-type <value>
  --targets <value>
  [--owner-information <value>]
  [--client-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--window-id`` (string)


  The ID of the Maintenance Window the target should be registered with.

  

``--resource-type`` (string)


  The type of target being registered with the Maintenance Window.

  

  Possible values:

  
  *   ``INSTANCE``

  

  

``--targets`` (list)


  The targets (either instances or tags). Instances are specified using Key=instanceids,Values=instanceid1,instanceid2. Tags are specified using Key=tag name,Values=tag value.

  



Shorthand Syntax::

    Key=string,Values=string,string ...




JSON Syntax::

  [
    {
      "Key": "string",
      "Values": ["string", ...]
    }
    ...
  ]



``--owner-information`` (string)


  User-provided value that will be included in any CloudWatch events raised while running tasks for these targets in this Maintenance Window.

  

``--client-token`` (string)


  User-provided idempotency token.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To register a single target with a maintenance window**

This example registers an instance with a maintenance window.

Command::

  aws ssm register-target-with-maintenance-window --window-id "mw-ab12cd34ef56gh78" --target "Key=InstanceIds,Values=i-0000293ffd8c57862" --owner-information "Single instance" --resource-type "INSTANCE"

Output::

  {
	"WindowTargetId":"1a2b3c4d-1a2b-1a2b-1a2b-1a2b3c4d-1a2"
  }

**To register multiple targets with a maintenance window**
	
This example registers two instances with a maintenance window.

Command::

  aws ssm register-target-with-maintenance-window --window-id "mw-ab12cd34ef56gh78" --target "Key=InstanceIds,Values=i-0000293ffd8c57862,i-0cb2b964d3e14fd9f" --owner-information "Two instances in a list" --resource-type "INSTANCE"

**To register a target with a maintenance window using EC2 tags**

This example registers an instance with a maintenance window using EC2 tags.

Command::

  aws ssm register-target-with-maintenance-window --window-id "mw-06cf17cbefcb4bf4f" --targets "Key=tag:Environment,Values=Prod" "Key=Role,Values=Web" --owner-information "Production Web Servers" --resource-type "INSTANCE"


======
Output
======

WindowTargetId -> (string)

  

  The ID of the target definition in this Maintenance Window.

  

  

