[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds describe-pending-maintenance-actions:


************************************
describe-pending-maintenance-actions
************************************



===========
Description
===========



Returns a list of resources (for example, DB instances) that have at least one pending maintenance action.



========
Synopsis
========

::

    describe-pending-maintenance-actions
  [--resource-identifier <value>]
  [--filters <value>]
  [--marker <value>]
  [--max-records <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--resource-identifier`` (string)


  The ARN of a resource to return pending maintenance actions for.

  

``--filters`` (list)


  A filter that specifies one or more resources to return pending maintenance actions for.

   

  Supported filters:

   

   
  * ``db-instance-id`` - Accepts DB instance identifiers and DB instance Amazon Resource Names (ARNs). The results list will only include pending maintenance actions for the DB instances identified by these ARNs.
   

  



Shorthand Syntax::

    Name=string,Values=string,string ...




JSON Syntax::

  [
    {
      "Name": "string",
      "Values": ["string", ...]
    }
    ...
  ]



``--marker`` (string)


  An optional pagination token provided by a previous ``describe-pending-maintenance-actions`` request. If this parameter is specified, the response includes only records beyond the marker, up to a number of records specified by ``MaxRecords`` . 

  

``--max-records`` (integer)


  The maximum number of records to include in the response. If more records exist than the specified ``MaxRecords`` value, a pagination token called a marker is included in the response so that the remaining results can be retrieved. 

   

  Default: 100

   

  Constraints: Minimum 20, maximum 100.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

PendingMaintenanceActions -> (list)

  

  A list of the pending maintenance actions for the resource.

  

  (structure)

    

    Describes the pending maintenance actions for a resource.

    

    ResourceIdentifier -> (string)

      

      The ARN of the resource that has pending maintenance actions.

      

      

    PendingMaintenanceActionDetails -> (list)

      

      A list that provides details about the pending maintenance actions for the resource.

      

      (structure)

        

        Provides information about a pending maintenance action for a resource.

        

        Action -> (string)

          

          The type of pending maintenance action that is available for the resource.

          

          

        AutoAppliedAfterDate -> (timestamp)

          

          The date of the maintenance window when the action will be applied. The maintenance action will be applied to the resource during its first maintenance window after this date. If this date is specified, any ``next-maintenance`` opt-in requests are ignored.

          

          

        ForcedApplyDate -> (timestamp)

          

          The date when the maintenance action will be automatically applied. The maintenance action will be applied to the resource on this date regardless of the maintenance window for the resource. If this date is specified, any ``immediate`` opt-in requests are ignored.

          

          

        OptInStatus -> (string)

          

          Indicates the type of opt-in request that has been received for the resource.

          

          

        CurrentApplyDate -> (timestamp)

          

          The effective date when the pending maintenance action will be applied to the resource. This date takes into account opt-in requests received from the  apply-pending-maintenance-action API, the ``AutoAppliedAfterDate`` , and the ``ForcedApplyDate`` . This value is blank if an opt-in request has not been received and nothing has been specified as ``AutoAppliedAfterDate`` or ``ForcedApplyDate`` .

          

          

        Description -> (string)

          

          A description providing more detail about the maintenance action.

          

          

        

      

    

  

Marker -> (string)

  

  An optional pagination token provided by a previous ``describe-pending-maintenance-actions`` request. If this parameter is specified, the response includes only records beyond the marker, up to a number of records specified by ``MaxRecords`` . 

  

  

