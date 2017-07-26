[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks describe-agent-versions:


***********************
describe-agent-versions
***********************



===========
Description
===========



Describes the available AWS OpsWorks Stacks agent versions. You must specify a stack ID or a configuration manager. ``describe-agent-versions`` returns a list of available agent versions for the specified stack or configuration manager.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworks-2013-02-18/DescribeAgentVersions>`_


========
Synopsis
========

::

    describe-agent-versions
  [--stack-id <value>]
  [--configuration-manager <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

        

        

      

    

  

