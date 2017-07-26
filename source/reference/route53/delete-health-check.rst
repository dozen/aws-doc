[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 delete-health-check:


*******************
delete-health-check
*******************



===========
Description
===========



Deletes a health check.

 

.. warning::

   

  Amazon Route 53 does not prevent you from deleting a health check even if the health check is associated with one or more resource record sets. If you delete a health check and you don't update the associated resource record sets, the future status of the health check can't be predicted and may change. This will affect the routing of DNS queries for your DNS failover configuration. For more information, see `Replacing and Deleting Health Checks <http://docs.aws.amazon.com/Route53/latest/DeveloperGuide/health-checks-creating-deleting.html#health-checks-deleting.html>`_ in the *Amazon Route 53 Developer Guide* .

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/route53-2013-04-01/DeleteHealthCheck>`_


========
Synopsis
========

::

    delete-health-check
  --health-check-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--health-check-id`` (string)


  The ID of the health check that you want to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To delete a health check**

The following ``delete-health-check`` command deletes the health check with a ``health-check-id`` of ``e75b48d9-547a-4c3d-88a5-ae4002397608``::

  aws route53 delete-health-check --health-check-id e75b48d9-547a-4c3d-88a5-ae4002397608


======
Output
======

