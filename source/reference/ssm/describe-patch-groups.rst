[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm describe-patch-groups:


*********************
describe-patch-groups
*********************



===========
Description
===========



Lists all patch groups that have been registered with patch baselines.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/DescribePatchGroups>`_


========
Synopsis
========

::

    describe-patch-groups
  [--max-results <value>]
  [--filters <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--max-results`` (integer)


  The maximum number of patch groups to return (per page).

  

``--filters`` (list)


  One or more filters. Use a filter to return a more specific list of results.

  



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



``--next-token`` (string)


  The token for the next set of items to return. (You received this token from a previous call.)

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To display patch group registrations**

This example lists the patch group registrations.

Command::

  aws ssm describe-patch-groups

Output::

  {
    "Mappings": [
        {
            "PatchGroup": "Production",
            "BaselineIdentity": {
                "BaselineName": "Production-Baseline",
                "DefaultBaseline": false,
                "BaselineDescription": "Baseline containing all updates approved for production systems",
                "BaselineId": "pb-045f10b4f382baeda"
            }
        }
    ]
  }


======
Output
======

Mappings -> (list)

  

  Each entry in the array contains:

   

  PatchGroup: string (between 1 and 256 characters, Regex: ^([\p{L}\p{Z}\p{N}_.:/=+\-@]*)$)

   

  PatchBaselineIdentity: A PatchBaselineIdentity element. 

  

  (structure)

    

    The mapping between a patch group and the patch baseline the patch group is registered with.

    

    PatchGroup -> (string)

      

      The name of the patch group registered with the patch baseline.

      

      

    BaselineIdentity -> (structure)

      

      The patch baseline the patch group is registered with.

      

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

  

  

