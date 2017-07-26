[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy batch-get-on-premises-instances:


*******************************
batch-get-on-premises-instances
*******************************



===========
Description
===========



Gets information about one or more on-premises instances.



========
Synopsis
========

::

    batch-get-on-premises-instances
  [--instance-names <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--instance-names`` (list)


  The names of the on-premises instances to get information about.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To get information about one or more on-premises instances**

This example gets information about two on-premises instances.

Command::

  aws deploy batch-get-on-premises-instances --instance-names AssetTag12010298EX AssetTag23121309EX

Output::

  {
    "instanceInfos": [
      {
        "iamUserArn": "arn:aws:iam::80398EXAMPLE:user/AWS/CodeDeploy/AssetTag12010298EX",
        "tags": [
          {
            "Value": "CodeDeployDemo-OnPrem",
            "Key": "Name"
          }
        ],
        "instanceName": "AssetTag12010298EX",
        "registerTime": 1425579465.228,
        "instanceArn": "arn:aws:codedeploy:us-west-2:80398EXAMPLE:instance/AssetTag12010298EX_4IwLNI2Alh"
      },
      {
        "iamUserArn": "arn:aws:iam::80398EXAMPLE:user/AWS/CodeDeploy/AssetTag23121309EX",
        "tags": [
          {
            "Value": "CodeDeployDemo-OnPrem",
            "Key": "Name"
          }
        ],
        "instanceName": "AssetTag23121309EX",
        "registerTime": 1425595585.988,
        "instanceArn": "arn:aws:codedeploy:us-west-2:80398EXAMPLE:instance/AssetTag23121309EX_PomUy64Was"
      }
    ]
  }

======
Output
======

instanceInfos -> (list)

  

  Information about the on-premises instances.

  

  (structure)

    

    Information about an on-premises instance.

    

    instanceName -> (string)

      

      The name of the on-premises instance.

      

      

    iamUserArn -> (string)

      

      The IAM user ARN associated with the on-premises instance.

      

      

    instanceArn -> (string)

      

      The ARN of the on-premises instance.

      

      

    registerTime -> (timestamp)

      

      The time that the on-premises instance was registered.

      

      

    deregisterTime -> (timestamp)

      

      If the on-premises instance was deregistered, the time that the on-premises instance was deregistered.

      

      

    tags -> (list)

      

      The tags that are currently associated with the on-premises instance.

      

      (structure)

        

        Information about a tag.

        

        Key -> (string)

          

          The tag's key.

          

          

        Value -> (string)

          

          The tag's value.

          

          

        

      

    

  

