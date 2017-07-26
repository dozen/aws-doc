[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 delete-hosted-zone:


******************
delete-hosted-zone
******************



===========
Description
===========



This action deletes a hosted zone. To delete a hosted zone, send a ``DELETE`` request to the ``/*Route 53 API version* /hostedzone/*hosted zone ID*`` resource.

 

For more information about deleting a hosted zone, see `Deleting a Hosted Zone`_ in the *Amazon Route 53 Developer Guide* .

 

.. warning::

  You can delete a hosted zone only if there are no resource record sets other than the default SOA record and NS resource record sets. If your hosted zone contains other resource record sets, you must delete them before you can delete your hosted zone. If you try to delete a hosted zone that contains other resource record sets, Amazon Route 53 will deny your request with a ``HostedZoneNotEmpty`` error. For information about deleting records from your hosted zone, see  change-resource-record-sets .



========
Synopsis
========

::

    delete-hosted-zone
  --id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--id`` (string)


  The ID of the hosted zone you want to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To delete a hosted zone**

The following ``delete-hosted-zone`` command deletes the hosted zone with an ``id`` of  ``Z36KTIQEXAMPLE``::

  aws route53 delete-hosted-zone --id Z36KTIQEXAMPLE



======
Output
======

ChangeInfo -> (structure)

  

  A complex type that contains the ID, the status, and the date and time of your delete request.

  

  Id -> (string)

    

    The ID of the request. Use this ID to track when the change has completed across all Amazon Route 53 DNS servers.

    

    

  Status -> (string)

    

    The current state of the request. ``PENDING`` indicates that this request has not yet been applied to all Amazon Route 53 DNS servers.

     

    Valid Values: ``PENDING`` | ``INSYNC`` 

    

    

  SubmittedAt -> (timestamp)

    

    The date and time the change was submitted, in the format ``YYYY-MM-DDThh:mm:ssZ`` , as specified in the ISO 8601 standard (for example, 2009-11-19T19:37:58Z). The ``Z`` after the time indicates that the time is listed in Coordinated Universal Time (UTC).

    

    

  Comment -> (string)

    

    A complex type that describes change information about changes made to your hosted zone.

     

    This element contains an ID that you use when performing a  get-change action to get detailed information about the change.

    

    

  



.. _Deleting a Hosted Zone: http://docs.aws.amazon.com/Route53/latest/DeveloperGuide/DeleteHostedZone.html
