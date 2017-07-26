[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm update-patch-baseline:


*********************
update-patch-baseline
*********************



===========
Description
===========



Modifies an existing patch baseline. Fields not specified in the request are left unchanged.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/UpdatePatchBaseline>`_


========
Synopsis
========

::

    update-patch-baseline
  --baseline-id <value>
  [--name <value>]
  [--global-filters <value>]
  [--approval-rules <value>]
  [--approved-patches <value>]
  [--approved-patches-compliance-level <value>]
  [--rejected-patches <value>]
  [--description <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--baseline-id`` (string)


  The ID of the patch baseline to update.

  

``--name`` (string)


  The name of the patch baseline.

  

``--global-filters`` (structure)


  A set of global filters used to exclude patches from the baseline.

  



JSON Syntax::

  {
    "PatchFilters": [
      {
        "Key": "PRODUCT"|"CLASSIFICATION"|"MSRC_SEVERITY"|"PATCH_ID"|"SECTION"|"PRIORITY"|"SEVERITY",
        "Values": ["string", ...]
      }
      ...
    ]
  }



``--approval-rules`` (structure)


  A set of rules used to include patches in the baseline.

  



JSON Syntax::

  {
    "PatchRules": [
      {
        "PatchFilterGroup": {
          "PatchFilters": [
            {
              "Key": "PRODUCT"|"CLASSIFICATION"|"MSRC_SEVERITY"|"PATCH_ID"|"SECTION"|"PRIORITY"|"SEVERITY",
              "Values": ["string", ...]
            }
            ...
          ]
        },
        "ComplianceLevel": "CRITICAL"|"HIGH"|"MEDIUM"|"LOW"|"INFORMATIONAL"|"UNSPECIFIED",
        "ApproveAfterDays": integer
      }
      ...
    ]
  }



``--approved-patches`` (list)


  A list of explicitly approved patches for the baseline.

  



Syntax::

  "string" "string" ...



``--approved-patches-compliance-level`` (string)


  Assigns a new compliance severity level to an existing patch baseline.

  

  Possible values:

  
  *   ``CRITICAL``

  
  *   ``HIGH``

  
  *   ``MEDIUM``

  
  *   ``LOW``

  
  *   ``INFORMATIONAL``

  
  *   ``UNSPECIFIED``

  

  

``--rejected-patches`` (list)


  A list of explicitly rejected patches for the baseline.

  



Syntax::

  "string" "string" ...



``--description`` (string)


  A description of the patch baseline.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To update a patch baseline**

This example adds two patches as rejected and one patch as approved to a patch baseline.

Command::

  aws ssm update-patch-baseline --baseline-id "pb-045f10b4f382baeda" --rejected-patches "KB2032276" "MS10-048" --approved-patches "KB2124261"

Output::

  {
    "BaselineId": "pb-045f10b4f382baeda",
    "Name": "Production-Baseline",
    "RejectedPatches": [
        "KB2032276",
        "MS10-048"
    ],
    "GlobalFilters": {
        "PatchFilters": []
    },
    "ApprovalRules": {
        "PatchRules": [
            {
                "PatchFilterGroup": {
                    "PatchFilters": [
                        {
                            "Values": [
                                "Critical",
                                "Important",
                                "Moderate"
                            ],
                            "Key": "MSRC_SEVERITY"
                        },
                        {
                            "Values": [
                                "SecurityUpdates",
                                "Updates",
                                "UpdateRollups",
                                "CriticalUpdates"
                            ],
                            "Key": "CLASSIFICATION"
                        }
                    ]
                },
                "ApproveAfterDays": 7
            }
        ]
    },
    "ModifiedDate": 1487872602.453,
    "CreatedDate": 1487870482.16,
    "ApprovedPatches": [
        "KB2124261"
    ],
    "Description": "Baseline containing all updates approved for production systems"
  }

**To rename a patch baseline**

This example renames a patch baseline.

Command::

  aws ssm update-patch-baseline --baseline-id "pb-00dbb759999aa2bc3" --name "Windows-Server-2012-R2-Important-and-Critical-Security-Updates"
  

======
Output
======

BaselineId -> (string)

  

  The ID of the deleted patch baseline.

  

  

Name -> (string)

  

  The name of the patch baseline.

  

  

OperatingSystem -> (string)

  

  The operating system rule used by the updated patch baseline.

  

  

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

  

  The compliance severity level assigned to the patch baseline after the update completed.

  

  

RejectedPatches -> (list)

  

  A list of explicitly rejected patches for the baseline.

  

  (string)

    

    

  

CreatedDate -> (timestamp)

  

  The date when the patch baseline was created.

  

  

ModifiedDate -> (timestamp)

  

  The date when the patch baseline was last modified.

  

  

Description -> (string)

  

  A description of the Patch Baseline.

  

  

