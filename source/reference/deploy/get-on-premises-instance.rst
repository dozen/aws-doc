[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy get-on-premises-instance:


************************
get-on-premises-instance
************************



===========
Description
===========



Gets information about an on-premises instance.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codedeploy-2014-10-06/GetOnPremisesInstance>`_


========
Synopsis
========

::

    get-on-premises-instance
  --instance-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--instance-name`` (string)


  The name of the on-premises instance about which to get information.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To get information about an on-premises instance**

This example gets information about an on-premises instance.

Command::

  aws deploy get-on-premises-instance --instance-name AssetTag12010298EX

Output::

  {
    "instanceInfo": {
      "iamUserArn": "arn:aws:iam::80398EXAMPLE:user/AWS/CodeDeploy/AssetTag12010298EX",
        "tags": [
          {
            "Value": "CodeDeployDemo-OnPrem",
            "Key": "Name"
          }
        ],
        "instanceName": "AssetTag12010298EX",
        "registerTime": 1425579465.228,
        "instanceArn": "arn:aws:codedeploy:us-east-1:80398EXAMPLE:instance/AssetTag12010298EX_4IwLNI2Alh"
    }
  }

======
Output
======

instanceInfo -> (structure)

  

  Information about the on-premises instance.

  

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

        

        

      

    

  

