[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm describe-patch-baselines:


************************
describe-patch-baselines
************************



===========
Description
===========



Lists the patch baselines in your AWS account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/DescribePatchBaselines>`_


========
Synopsis
========

::

    describe-patch-baselines
  [--filters <value>]
  [--max-results <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--filters`` (list)


  Each element in the array is a structure containing: 

   

  Key: (string, "NAME_PREFIX" or "OWNER")

   

  Value: (array of strings, exactly 1 entry, between 1 and 255 characters)

  



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



``--max-results`` (integer)


  The maximum number of patch baselines to return (per page).

  

``--next-token`` (string)


  The token for the next set of items to return. (You received this token from a previous call.)

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To list all patch baselines**

This example lists all patch baselines.

Command::

  aws ssm describe-patch-baselines

Output::

  {
    "BaselineIdentities": [
        {
            "BaselineName": "AWS-DefaultPatchBaseline",
            "DefaultBaseline": true,
            "BaselineDescription": "Default Patch Baseline Provided by AWS.",
            "BaselineId": "arn:aws:ssm:us-west-2:812345678901:patchbaseline/pb-04fb4ae6142167966"
        },
        {
            "BaselineName": "Production-Baseline",
            "DefaultBaseline": false,
            "BaselineDescription": "Baseline containing all updates approved for production systems",
            "BaselineId": "pb-045f10b4f382baeda"
        },
        {
            "BaselineName": "Production-Baseline",
            "DefaultBaseline": false,
            "BaselineDescription": "Baseline containing all updates approved for production systems",
            "BaselineId": "pb-0a2f1059b670ebd31"
        }
    ]
  }


**To list all AWS provided patch baselines**

This example lists all patch baselines provided by AWS.

Command::

  aws ssm describe-patch-baselines --filters "Key=OWNER,Values=[AWS]"
  
**To list all patch baselines you own**

This example lists all patch baselines with you as the owner.

Command::

  aws ssm describe-patch-baselines --filters "Key=OWNER,Values=[Self]"


======
Output
======

BaselineIdentities -> (list)

  

  An array of PatchBaselineIdentity elements.

  

  (structure)

    

    Defines the basic information about a patch baseline.

    

    BaselineId -> (string)

      

      The ID of the patch baseline.

      

      

    BaselineName -> (string)

      

      The name of the patch baseline.

      

      

    OperatingSystem -> (string)

      

      Defines the operating system the patch baseline applies to. Supported operating systems include WINDOWS, AMAZON_LINUX, UBUNTU and REDHAT_ENTERPRISE_LINUX. The Default value is WINDOWS. 

      

      

    BaselineDescription -> (string)

      

      The description of the patch baseline.

      

      

    DefaultBaseline -> (boolean)

      

      Whether this is the default baseline. Note that Systems Manager supports creating multiple default patch baselines. For example, you can create a default patch baseline for each operating system.

      

      

    

  

NextToken -> (string)

  

  The token to use when requesting the next set of items. If there are no additional items to return, the string is empty.

  

  

