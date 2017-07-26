[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm describe-effective-patches-for-patch-baseline:


*********************************************
describe-effective-patches-for-patch-baseline
*********************************************



===========
Description
===========



Retrieves the current effective patches (the patch and the approval state) for the specified patch baseline. Note that this API applies only to Windows patch baselines.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/DescribeEffectivePatchesForPatchBaseline>`_


========
Synopsis
========

::

    describe-effective-patches-for-patch-baseline
  --baseline-id <value>
  [--max-results <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--baseline-id`` (string)


  The ID of the patch baseline to retrieve the effective patches for.

  

``--max-results`` (integer)


  The maximum number of patches to return (per page).

  

``--next-token`` (string)


  The token for the next set of items to return. (You received this token from a previous call.)

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To get all patches defined by a patch baseline**

This example returns the patches defined by a patch baseline.

Command::

  aws ssm describe-effective-patches-for-patch-baseline --baseline-id "pb-08b654cf9b9681f04"
  
Output::

  {
    "NextToken": "--token string truncated--": [
        {
            "PatchStatus": {
                "ApprovalDate": 1292954400.0,
                "DeploymentStatus": "APPROVED"
            },
            "Patch": {
                "ContentUrl": "https://support.microsoft.com/en-us/kb/2207559",
                "ProductFamily": "Windows",
                "Product": "WindowsServer2008R2",
                "Vendor": "Microsoft",
                "Description": "A security issue has been identified that could allow an authenticated remote attacker to cause the affected system to stop responding. You can help protect your system by installing this update from Microsoft. After you install this update, you may have to restart your system.",
                "Classification": "SecurityUpdates",
                "Title": "Security Update for Windows Server 2008 R2 x64 Edition (KB2207559)",
                "ReleaseDate": 1292349600.0,
                "Language": "All",
                "MsrcSeverity": "Important",
                "KbNumber": "KB2207559",
                "MsrcNumber": "MS10-101",
                "Id": "79d0c8b2-5b35-4455-bfa3-89e0f08fa980"
            }
        },
        {
            "PatchStatus": {
                "ApprovalDate": 1285088400.0,
                "DeploymentStatus": "APPROVED"
            },
        ...
	}
  }


======
Output
======

EffectivePatches -> (list)

  

  An array of patches and patch status.

  

  (structure)

    

    The EffectivePatch structure defines metadata about a patch along with the approval state of the patch in a particular patch baseline. The approval state includes information about whether the patch is currently approved, due to be approved by a rule, explicitly approved, or explicitly rejected and the date the patch was or will be approved.

    

    Patch -> (structure)

      

      Provides metadata for a patch, including information such as the KB ID, severity, classification and a URL for where more information can be obtained about the patch.

      

      Id -> (string)

        

        The ID of the patch (this is different than the Microsoft Knowledge Base ID).

        

        

      ReleaseDate -> (timestamp)

        

        The date the patch was released.

        

        

      Title -> (string)

        

        The title of the patch.

        

        

      Description -> (string)

        

        The description of the patch.

        

        

      ContentUrl -> (string)

        

        The URL where more information can be obtained about the patch.

        

        

      Vendor -> (string)

        

        The name of the vendor providing the patch.

        

        

      ProductFamily -> (string)

        

        The product family the patch is applicable for (for example, Windows).

        

        

      Product -> (string)

        

        The specific product the patch is applicable for (for example, WindowsServer2016).

        

        

      Classification -> (string)

        

        The classification of the patch (for example, SecurityUpdates, Updates, CriticalUpdates).

        

        

      MsrcSeverity -> (string)

        

        The severity of the patch (for example Critical, Important, Moderate).

        

        

      KbNumber -> (string)

        

        The Microsoft Knowledge Base ID of the patch.

        

        

      MsrcNumber -> (string)

        

        The ID of the MSRC bulletin the patch is related to.

        

        

      Language -> (string)

        

        The language of the patch if it's language-specific.

        

        

      

    PatchStatus -> (structure)

      

      The status of the patch in a patch baseline. This includes information about whether the patch is currently approved, due to be approved by a rule, explicitly approved, or explicitly rejected and the date the patch was or will be approved.

      

      DeploymentStatus -> (string)

        

        The approval status of a patch (APPROVED, PENDING_APPROVAL, EXPLICIT_APPROVED, EXPLICIT_REJECTED).

        

        

      ComplianceLevel -> (string)

        

        The compliance severity level for a patch.

        

        

      ApprovalDate -> (timestamp)

        

        The date the patch was approved (or will be approved if the status is PENDING_APPROVAL).

        

        

      

    

  

NextToken -> (string)

  

  The token to use when requesting the next set of items. If there are no additional items to return, the string is empty.

  

  

