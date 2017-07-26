[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds apply-pending-maintenance-action:


********************************
apply-pending-maintenance-action
********************************



===========
Description
===========



Applies a pending maintenance action to a resource (for example, to a DB instance).



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rds-2014-10-31/ApplyPendingMaintenanceAction>`_


========
Synopsis
========

::

    apply-pending-maintenance-action
  --resource-identifier <value>
  --apply-action <value>
  --opt-in-type <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--resource-identifier`` (string)


  The RDS Amazon Resource Name (ARN) of the resource that the pending maintenance action applies to. For information about creating an ARN, see `Constructing an RDS Amazon Resource Name (ARN) <http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_Tagging.ARN.html#USER_Tagging.ARN.Constructing>`_ .

  

``--apply-action`` (string)


  The pending maintenance action to apply to this resource.

   

  Valid values: ``system-update`` , ``db-upgrade``  

  

``--opt-in-type`` (string)


  A value that specifies the type of opt-in request, or undoes an opt-in request. An opt-in request of type ``immediate`` cannot be undone.

   

  Valid values:

   

   
  * ``immediate`` - Apply the maintenance action immediately. 
   
  * ``next-maintenance`` - Apply the maintenance action during the next maintenance window for the resource. 
   
  * ``undo-opt-in`` - Cancel any existing ``next-maintenance`` opt-in requests. 
   

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ResourcePendingMaintenanceActions -> (structure)

  

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

        

        

      

    

  

