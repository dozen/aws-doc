[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 delete-health-check:


*******************
delete-health-check
*******************



===========
Description
===========



This action deletes a health check. To delete a health check, send a ``DELETE`` request to the ``/*Route 53 API version* /healthcheck/*health check ID*`` resource.

 

.. warning::

  You can delete a health check only if there are no resource record sets associated with this health check. If resource record sets are associated with this health check, you must disassociate them before you can delete your health check. If you try to delete a health check that is associated with resource record sets, Amazon Route 53 will deny your request with a ``HealthCheckInUse`` error. For information about disassociating the records from your health check, see  change-resource-record-sets .



========
Synopsis
========

::

    delete-health-check
  --health-check-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--health-check-id`` (string)


  The ID of the health check to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To delete a health check**

The following ``delete-health-check`` command deletes the health check with a ``health-check-id`` of ``e75b48d9-547a-4c3d-88a5-ae4002397608``::

  aws route53 delete-health-check --health-check-id e75b48d9-547a-4c3d-88a5-ae4002397608


======
Output
======

