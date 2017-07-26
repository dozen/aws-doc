[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 get-change:


**********
get-change
**********



===========
Description
===========



Returns the current status of a change batch request. The status is one of the following values:

 

 
* ``PENDING`` indicates that the changes in this request have not propagated to all Amazon Route 53 DNS servers. This is the initial status of all change batch requests. 
 
* ``INSYNC`` indicates that the changes have propagated to all Amazon Route 53 DNS servers.  
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/route53-2013-04-01/GetChange>`_


========
Synopsis
========

::

    get-change
  --id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--id`` (string)


  The ID of the change batch request. The value that you specify here is the value that ``change-resource-record-sets`` returned in the ``Id`` element when you submitted the request.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

  

  A complex type that contains information about the specified change batch.

  

  Id -> (string)

    

    The ID of the request.

    

    

  Status -> (string)

    

    The current state of the request. ``PENDING`` indicates that this request has not yet been applied to all Amazon Route 53 DNS servers.

    

    

  SubmittedAt -> (timestamp)

    

    The date and time that the change request was submitted in `ISO 8601 format <https://en.wikipedia.org/wiki/ISO_8601>`_ and Coordinated Universal Time (UTC). For example, the value ``2017-03-27T17:48:16.751Z`` represents March 27, 2017 at 17:48:16.751 UTC.

    

    

  Comment -> (string)

    

    A complex type that describes change information about changes made to your hosted zone.

     

    This element contains an ID that you use when performing a  get-change action to get detailed information about the change.

    

    

  

