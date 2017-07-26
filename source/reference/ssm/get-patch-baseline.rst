[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm get-patch-baseline:


******************
get-patch-baseline
******************



===========
Description
===========



Retrieves information about a patch baseline.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/GetPatchBaseline>`_


========
Synopsis
========

::

    get-patch-baseline
  --baseline-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--baseline-id`` (string)


  The ID of the patch baseline to retrieve.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To display a patch baseline**

This example displays the details for a patch baseline.

Command::

  aws ssm get-patch-baseline --baseline-id "pb-00dbb759999aa2bc3"

Output::

  {
	"BaselineId":"pb-00dbb759999aa2bc3",
	"Name":"Windows-Server-2012R2",
	"PatchGroups":[
		"Web Servers"
	],
	"RejectedPatches":[
	
	],
	"GlobalFilters":{
		"PatchFilters":[
	
		]
	},
	"ApprovalRules":{
		"PatchRules":[
			{
				"PatchFilterGroup":{
				"PatchFilters":[
					{
						"Values":[
							"Important",
							"Critical"
						],
						"Key":"MSRC_SEVERITY"
					},
					{
						"Values":[
							"SecurityUpdates"
						],
						"Key":"CLASSIFICATION"
					},
					{
						"Values":[
							"WindowsServer2012R2"
						],
						"Key":"PRODUCT"
					}
				]
				},
				"ApproveAfterDays":5
			}
		]
	},
	"ModifiedDate":1480997823.81,
	"CreatedDate":1480997823.81,
	"ApprovedPatches":[
	
	],
	"Description":"Windows Server 2012 R2, Important and Critical security updates"
  }


======
Output
======

BaselineId -> (string)

  

  The ID of the retrieved patch baseline.

  

  

Name -> (string)

  

  The name of the patch baseline.

  

  

OperatingSystem -> (string)

  

  Returns the operating system specified for the patch baseline.

  

  

GlobalFilters -> (structure)

  

  A set of global filters used to exclude patches from the baseline.

  

  PatchFilters -> (list)

    

    The set of patch filters that make up the group.

    

    (structure)

      

      Defines a patch filter.

      

      Key -> (string)

        

        The key for the filter (PRODUCT, CLASSIFICATION, MSRC_SEVERITY, PATCH_ID)

        

        

      Values -> (list)

        

        The value for the filter key.

        

        (string)

          

          

        

      

    

  

ApprovalRules -> (structure)

  

  A set of rules used to include patches in the baseline.

  

  PatchRules -> (list)

    

    The rules that make up the rule group.

    

    (structure)

      

      Defines an approval rule for a patch baseline.

      

      PatchFilterGroup -> (structure)

        

        The patch filter group that defines the criteria for the rule.

        

        PatchFilters -> (list)

          

          The set of patch filters that make up the group.

          

          (structure)

            

            Defines a patch filter.

            

            Key -> (string)

              

              The key for the filter (PRODUCT, CLASSIFICATION, MSRC_SEVERITY, PATCH_ID)

              

              

            Values -> (list)

              

              The value for the filter key.

              

              (string)

                

                

              

            

          

        

      ComplianceLevel -> (string)

        

        A compliance severity level for all approved patches in a patch baseline. Valid compliance severity levels include the following: Unspecified, Critical, High, Medium, Low, and Informational.

        

        

      ApproveAfterDays -> (integer)

        

        The number of days after the release date of each patch matched by the rule the patch is marked as approved in the patch baseline.

        

        

      

    

  

ApprovedPatches -> (list)

  

  A list of explicitly approved patches for the baseline.

  

  (string)

    

    

  

ApprovedPatchesComplianceLevel -> (string)

  

  Returns the specified compliance severity level for approved patches in the patch baseline.

  

  

RejectedPatches -> (list)

  

  A list of explicitly rejected patches for the baseline.

  

  (string)

    

    

  

PatchGroups -> (list)

  

  Patch groups included in the patch baseline.

  

  (string)

    

    

  

CreatedDate -> (timestamp)

  

  The date the patch baseline was created.

  

  

ModifiedDate -> (timestamp)

  

  The date the patch baseline was last modified.

  

  

Description -> (string)

  

  A description of the patch baseline.

  

  

