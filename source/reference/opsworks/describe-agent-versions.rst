[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks describe-agent-versions:


***********************
describe-agent-versions
***********************



===========
Description
===========



Describes the available AWS OpsWorks agent versions. You must specify a stack ID or a configuration manager. ``describe-agent-versions`` returns a list of available agent versions for the specified stack or configuration manager.



========
Synopsis
========

::

    describe-agent-versions
  [--stack-id <value>]
  [--configuration-manager <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--stack-id`` (string)


  The stack ID.

  

``--configuration-manager`` (structure)


  The configuration manager.

  



Shorthand Syntax::

    Name=string,Version=string




JSON Syntax::

  {
    "Name": "string",
    "Version": "string"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

AgentVersions -> (list)

  

  The agent versions for the specified stack or configuration manager. Note that this value is the complete version number, not the abbreviated number used by the console.

  

  (structure)

    

    Describes an agent version.

    

    Version -> (string)

      

      The agent version.

      

      

    ConfigurationManager -> (structure)

      

      The configuration manager.

      

      Name -> (string)

        

        The name. This parameter must be set to "Chef".

        

        

      Version -> (string)

        

        The Chef version. This parameter must be set to 12, 11.10, or 11.4 for Linux stacks, and to 12.2 for Windows stacks. The default value for Linux stacks is 11.4.

        

        

      

    

  

