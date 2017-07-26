[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm create-patch-baseline:


*********************
create-patch-baseline
*********************



===========
Description
===========



Creates a patch baseline.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/CreatePatchBaseline>`_


========
Synopsis
========

::

    create-patch-baseline
  [--operating-system <value>]
  --name <value>
  [--global-filters <value>]
  [--approval-rules <value>]
  [--approved-patches <value>]
  [--approved-patches-compliance-level <value>]
  [--rejected-patches <value>]
  [--description <value>]
  [--client-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--operating-system`` (string)


  Defines the operating system the patch baseline applies to. Supported operating systems include WINDOWS, AMAZON_LINUX, UBUNTU and REDHAT_ENTERPRISE_LINUX. The Default value is WINDOWS.

  

  Possible values:

  
  *   ``WINDOWS``

  
  *   ``AMAZON_LINUX``

  
  *   ``UBUNTU``

  
  *   ``REDHAT_ENTERPRISE_LINUX``

  

  

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


  Defines the compliance level for approved patches. This means that if an approved patch is reported as missing, this is the severity of the compliance violation. Valid compliance severity levels include the following: CRITICAL, HIGH, MEDIUM, LOW, INFORMATIONAL, UNSPECIFIED. The default value is UNSPECIFIED.

  

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

  

``--client-token`` (string)


  User-provided idempotency token.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create a patch baseline**

This example creates a patch baseline that approves patches for a production environment seven days after they are released by Microsoft.

Command::

  aws ssm create-patch-baseline --name "Production-Baseline" --approval-rules "PatchRules=[{PatchFilterGroup={PatchFilters=[{Key=MSRC_SEVERITY,Values=[Critical,Important,Moderate]},{Key=CLASSIFICATION,Values=[SecurityUpdates,Updates,UpdateRollups,CriticalUpdates]}]},ApproveAfterDays=7}]" --description "Baseline containing all updates approved for production systems"

Output::

  {
    "BaselineId": "pb-045f10b4f382baeda"
  }


======
Output
======

BaselineId -> (string)

  

  The ID of the created patch baseline.

  

  

