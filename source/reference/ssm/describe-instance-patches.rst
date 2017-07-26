[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm describe-instance-patches:


*************************
describe-instance-patches
*************************



===========
Description
===========



Retrieves information about the patches on the specified instance and their state relative to the patch baseline being used for the instance.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/DescribeInstancePatches>`_


========
Synopsis
========

::

    describe-instance-patches
  --instance-id <value>
  [--filters <value>]
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--instance-id`` (string)


  The ID of the instance whose patch state information should be retrieved.

  

``--filters`` (list)


  Each entry in the array is a structure containing:

   

  Key (string, between 1 and 128 characters)

   

  Values (array of strings, each string between 1 and 256 characters)

  



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

  

``--max-results`` (integer)


  The maximum number of patches to return (per page).

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To get the patch compliance details for an instance**

This example gets the patch compliance details for an instance.

Command::

  aws ssm describe-instance-patches --instance-id "i-08ee91c0b17045407"

Output::

  {
	"NextToken":"--token string truncated--",
	"Patches":[
		{
			"KBId":"KB2919355",
			"Severity":"Critical",
			"Classification":"SecurityUpdates",
			"Title":"Windows 8.1 Update for x64-based Systems (KB2919355)",
			"State":"Installed",
			"InstalledTime":"2014-03-18T12:00:00Z"
		},
		{
			"KBId":"KB2977765",
			"Severity":"Important",
			"Classification":"SecurityUpdates",
			"Title":"Security Update for Microsoft .NET Framework 4.5.1 and 4.5.2 on Windows 8.1 and Windows Server 2012 R2 x64-based Systems (KB2977765)",
			"State":"Installed",
			"InstalledTime":"2014-10-15T12:00:00Z"
		},
		{
			"KBId":"KB2978126",
			"Severity":"Important",
			"Classification":"SecurityUpdates",
			"Title":"Security Update for Microsoft .NET Framework 4.5.1 and 4.5.2 on Windows 8.1 (KB2978126)",
			"State":"Installed",
			"InstalledTime":"2014-11-18T12:00:00Z"
		},
		---output truncated---


======
Output
======

Patches -> (list)

  

  Each entry in the array is a structure containing:

   

  Title (string)

   

  KBId (string)

   

  Classification (string)

   

  Severity (string)

   

  State (string: "INSTALLED", "INSTALLED OTHER", "MISSING", "NOT APPLICABLE", "FAILED")

   

  InstalledTime (DateTime)

   

  InstalledBy (string)

  

  (structure)

    

    Information about the state of a patch on a particular instance as it relates to the patch baseline used to patch the instance.

    

    Title -> (string)

      

      The title of the patch.

      

      

    KBId -> (string)

      

      The operating system-specific ID of the patch.

      

      

    Classification -> (string)

      

      The classification of the patch (for example, SecurityUpdates, Updates, CriticalUpdates).

      

      

    Severity -> (string)

      

      The severity of the patch (for example, Critical, Important, Moderate).

      

      

    State -> (string)

      

      The state of the patch on the instance (INSTALLED, INSTALLED_OTHER, MISSING, NOT_APPLICABLE or FAILED).

      

      

    InstalledTime -> (timestamp)

      

      The date/time the patch was installed on the instance. Note that not all operating systems provide this level of information.

      

      

    

  

NextToken -> (string)

  

  The token to use when requesting the next set of items. If there are no additional items to return, the string is empty.

  

  

