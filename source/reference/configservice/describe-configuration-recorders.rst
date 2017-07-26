[ :ref:`aws <cli:aws>` . :ref:`configservice <cli:aws configservice>` ]

.. _cli:aws configservice describe-configuration-recorders:


********************************
describe-configuration-recorders
********************************



===========
Description
===========



Returns the name of one or more specified configuration recorders. If the recorder name is not specified, this action returns the names of all the configuration recorders associated with the account. 

 

.. note::

   

  Currently, you can specify only one configuration recorder per account.

   



========
Synopsis
========

::

    describe-configuration-recorders
  [--configuration-recorder-names <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--configuration-recorder-names`` (list)


  A list of configuration recorder names.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To get details about the configuration recorder**

The following command returns details about the default configuration recorder::

    aws configservice describe-configuration-recorders

Output::

    {
        "ConfigurationRecorders": [
            {
                "recordingGroup": {
                    "allSupported": true,
                    "resourceTypes": [],
                    "includeGlobalResourceTypes": true
                },
                "roleARN": "arn:aws:iam::123456789012:role/config-ConfigRole-A1B2C3D4E5F6",
                "name": "default"
            }
        ]
    }

======
Output
======

ConfigurationRecorders -> (list)

  

  A list that contains the descriptions of the specified configuration recorders.

  

  (structure)

    

    An object that represents the recording of configuration changes of an AWS resource.

    

    name -> (string)

      

      The name of the recorder. By default, AWS Config automatically assigns the name defaultwhen creating the configuration recorder. You cannot change the assigned name.

      

      

    roleARN -> (string)

      

      Amazon Resource Name (ARN) of the IAM role used to describe the AWS resources associated with the account.

      

      

    recordingGroup -> (structure)

      

      Specifies the types of AWS resource for which AWS Config records configuration changes.

      

      allSupported -> (boolean)

        

        Specifies whether AWS Config records configuration changes for every supported type of regional resource.

         

        If you set this option to ``true`` , when AWS Config adds support for a new type of regional resource, it automatically starts recording resources of that type.

         

        If you set this option to ``true`` , you cannot enumerate a list of ``resourceTypes`` .

        

        

      includeGlobalResourceTypes -> (boolean)

        

        Specifies whether AWS Config includes all supported types of global resources with the resources that it records.

         

        Before you can set this option to ``true`` , you must set the ``allSupported`` option to ``true`` .

         

        If you set this option to ``true`` , when AWS Config adds support for a new type of global resource, it automatically starts recording resources of that type.

        

        

      resourceTypes -> (list)

        

        A comma-separated list that specifies the types of AWS resources for which AWS Config records configuration changes (for example, ``AWS::EC2::Instance`` or ``AWS::CloudTrail::Trail`` ).

         

        Before you can set this option to ``true`` , you must set the ``allSupported`` option to ``false`` .

         

        If you set this option to ``true`` , when AWS Config adds support for a new type of resource, it will not record resources of that type unless you manually add that type to your recording group.

         

        For a list of valid ``resourceTypes`` values, see the **resourceType Value** column in `Supported AWS Resource Types`_ .

        

        (string)

          

          

        

      

    

  



.. _Supported AWS Resource Types: http://docs.aws.amazon.com/config/latest/developerguide/resource-config-reference.html#supported-resources
