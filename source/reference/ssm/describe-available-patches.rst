[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm describe-available-patches:


**************************
describe-available-patches
**************************



===========
Description
===========



Lists all patches that could possibly be included in a patch baseline.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/DescribeAvailablePatches>`_


========
Synopsis
========

::

    describe-available-patches
  [--filters <value>]
  [--max-results <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--filters`` (list)


  Filters used to scope down the returned patches.

  



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

**To get available patches**

This example gets all available patches for Windows Server 2012 that have a MSRC severity of Critical.

Command::

  aws ssm describe-available-patches --filters "Key=PRODUCT,Values=WindowsServer2012" "Key=MSRC_SEVERITY,Values=Critical"

Output::

  {
    "Patches": [
        {
            "ContentUrl": "https://support.microsoft.com/en-us/kb/2727528",
            "ProductFamily": "Windows",
            "Product": "WindowsServer2012",
            "Vendor": "Microsoft",
            "Description": "A security issue has been identified that could allow an unauthenticated remote attacker to compromise your system and gain control over it. You can help protect your system by installing this update from Microsoft. After you install this update, you may have to restart your system.",
            "Classification": "SecurityUpdates",
            "Title": "Security Update for Windows Server 2012 (KB2727528)",
            "ReleaseDate": 1352829600.0,
            "Language": "All",
            "MsrcSeverity": "Critical",
            "KbNumber": "KB2727528",
            "MsrcNumber": "MS12-072",
            "Id": "1eb507be-2040-4eeb-803d-abc55700b715"
        },
        {
            "ContentUrl": "https://support.microsoft.com/en-us/kb/2729462",
            "ProductFamily": "Windows",
            "Product": "WindowsServer2012",
            "Vendor": "Microsoft",
            "Description": "A security issue has been identified that could allow an unauthenticated remote attacker to compromise your system and gain control over it. You can help protect your system by installing this update from Microsoft. After you install this update, you may have to restart your system.",
            "Classification": "SecurityUpdates",
            "Title": "Security Update for Microsoft .NET Framework 3.5 on Windows 8 and Windows Server 2012 for x64-based Systems (KB2729462)",
            "ReleaseDate": 1352829600.0,
            "Language": "All",
            "MsrcSeverity": "Critical",
            "KbNumber": "KB2729462",
            "MsrcNumber": "MS12-074",
            "Id": "af873760-c97c-4088-ab7e-5219e120eab4"
        },
		...
	}
  }

======
Output
======

Patches -> (list)

  

  An array of patches. Each entry in the array is a patch structure.

  

  (structure)

    

    Represents metadata about a patch.

    

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

      

      

    

  

NextToken -> (string)

  

  The token to use when requesting the next set of items. If there are no additional items to return, the string is empty.

  

  

