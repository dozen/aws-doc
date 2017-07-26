[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy get-on-premises-instance:


************************
get-on-premises-instance
************************



===========
Description
===========



Gets information about an on-premises instance.



========
Synopsis
========

::

    get-on-premises-instance
  --instance-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--instance-name`` (string)


  The name of the on-premises instance to get information about

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

        

        

      

    

  

