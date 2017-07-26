[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 get-change:


**********
get-change
**********



===========
Description
===========



This action returns the current status of a change batch request. The status is one of the following values:

 

- ``PENDING`` indicates that the changes in this request have not replicated to all Amazon Route 53 DNS servers. This is the initial status of all change batch requests.

 

- ``INSYNC`` indicates that the changes have replicated to all Amazon Route 53 DNS servers. 



========
Synopsis
========

::

    get-change
  --id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--id`` (string)


  The ID of the change batch request. The value that you specify here is the value that ``change-resource-record-sets`` returned in the Id element when you submitted the request.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To get the status of a change to resource record sets**

The following ``get-change`` command gets the status and other information about the ``change-resource-record-sets`` request that has an ``Id`` of ``/change/CWPIK4URU2I5S``::

  aws route53 get-change --id /change/CWPIK4URU2I5S



======
Output
======

ChangeInfo -> (structure)

  

  A complex type that contains information about the specified change batch, including the change batch ID, the status of the change, and the date and time of the request.

  

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

    

    

  

