[ :ref:`aws <cli:aws>` . :ref:`batch <cli:aws batch>` ]

.. _cli:aws batch register-job-definition:


***********************
register-job-definition
***********************



===========
Description
===========



Registers an AWS Batch job definition. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/batch-2016-08-10/RegisterJobDefinition>`_


========
Synopsis
========

::

    register-job-definition
  --job-definition-name <value>
  --type <value>
  [--parameters <value>]
  [--container-properties <value>]
  [--retry-strategy <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--job-definition-name`` (string)


  The name of the job definition to register. 

  

``--type`` (string)


  The type of job definition.

  

  Possible values:

  
  *   ``container``

  

  

``--parameters`` (map)


  Default parameter substitution placeholders to set in the job definition. Parameters are specified as a key-value pair mapping. Parameters in a ``submit-job`` request override any corresponding parameter defaults from the job definition.

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``--container-properties`` (structure)


  An object with various properties specific for container-based jobs. This parameter is required if the ``type`` parameter is ``container`` .

  



JSON Syntax::

  {
    "image": "string",
    "vcpus": integer,
    "memory": integer,
    "command": ["string", ...],
    "jobRoleArn": "string",
    "volumes": [
      {
        "host": {
          "sourcePath": "string"
        },
        "name": "string"
      }
      ...
    ],
    "environment": [
      {
        "name": "string",
        "value": "string"
      }
      ...
    ],
    "mountPoints": [
      {
        "containerPath": "string",
        "readOnly": true|false,
        "sourceVolume": "string"
      }
      ...
    ],
    "readonlyRootFilesystem": true|false,
    "privileged": true|false,
    "ulimits": [
      {
        "hardLimit": integer,
        "name": "string",
        "softLimit": integer
      }
      ...
    ],
    "user": "string"
  }



``--retry-strategy`` (structure)


  The retry strategy to use for failed jobs that are submitted with this job definition. Any retry strategy that is specified during a  submit-job operation overrides the retry strategy defined here.

  



Shorthand Syntax::

    attempts=integer




JSON Syntax::

  {
    "attempts": integer
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To register a job definition**

This example registers a job definition for a simple container job.

Command::

  aws batch register-job-definition --job-definition-name sleep30 --type container --container-properties '{ "image": "busybox", "vcpus": 1, "memory": 128, "command": [ "sleep", "30"]}'

Output::

  {
      "jobDefinitionArn": "arn:aws:batch:us-east-1:012345678910:job-definition/sleep30:1",
      "jobDefinitionName": "sleep30",
      "revision": 1
  }


======
Output
======

jobDefinitionName -> (string)

  

  The name of the job definition. 

  

  

jobDefinitionArn -> (string)

  

  The Amazon Resource Name (ARN) of the job definition. 

  

  

revision -> (integer)

  

  The revision of the job definition.

  

  

