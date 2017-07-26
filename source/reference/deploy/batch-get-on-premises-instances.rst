[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy batch-get-on-premises-instances:


*******************************
batch-get-on-premises-instances
*******************************



===========
Description
===========



Gets information about one or more on-premises instances.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codedeploy-2014-10-06/BatchGetOnPremisesInstances>`_


========
Synopsis
========

::

    batch-get-on-premises-instances
  [--instance-names <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--instance-names`` (list)


  The names of the on-premises instances about which to get information.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

      

      

    iamSessionArn -> (string)

      

      The ARN of the IAM session associated with the on-premises instance.

      

      

    iamUserArn -> (string)

      

      The IAM user ARN associated with the on-premises instance.

      

      

    instanceArn -> (string)

      

      The ARN of the on-premises instance.

      

      

    registerTime -> (timestamp)

      

      The time at which the on-premises instance was registered.

      

      

    deregisterTime -> (timestamp)

      

      If the on-premises instance was deregistered, the time at which the on-premises instance was deregistered.

      

      

    tags -> (list)

      

      The tags currently associated with the on-premises instance.

      

      (structure)

        

        Information about a tag.

        

        Key -> (string)

          

          The tag's key.

          

          

        Value -> (string)

          

          The tag's value.

          

          

        

      

    

  

