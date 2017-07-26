[ :ref:`aws <cli:aws>` . :ref:`waf <cli:aws waf>` ]

.. _cli:aws waf update-ip-set:


*************
update-ip-set
*************



===========
Description
===========



Inserts or deletes  IPSetDescriptor objects in an ``IPSet`` . For each ``IPSetDescriptor`` object, you specify the following values: 

 

 
* Whether to insert or delete the object from the array. If you want to change an ``IPSetDescriptor`` object, you delete the existing object and add a new one.
 
* The IP address version, ``IPv4`` . 
 
* The IP address in CIDR notation, for example, ``192.0.2.0/24`` (for the range of IP addresses from ``192.0.2.0`` to ``192.0.2.255`` ) or ``192.0.2.44/32`` (for the individual IP address ``192.0.2.44`` ). 
 

 

AWS WAF supports /8, /16, /24, and /32 IP address ranges. For more information about CIDR notation, see the Wikipedia entry `Classless Inter-Domain Routing`_ .

 

You use an ``IPSet`` to specify which web requests you want to allow or block based on the IP addresses that the requests originated from. For example, if you're receiving a lot of requests from one or a small number of IP addresses and you want to block the requests, you can create an ``IPSet`` that specifies those IP addresses, and then configure AWS WAF to block the requests. 

 

To create and configure an ``IPSet`` , perform the following steps:

 

 
* Submit a  create-ip-set request.
 
* Use  get-change-token to get the change token that you provide in the ``change-token`` parameter of an  update-ip-set request.
 
* Submit an ``update-ip-set`` request to specify the IP addresses that you want AWS WAF to watch for.
 

 

When you update an ``IPSet`` , you specify the IP addresses that you want to add and/or the IP addresses that you want to delete. If you want to change an IP address, you delete the existing IP address and add the new one.

 

For more information about how to use the AWS WAF API to allow or block HTTP requests, see the `AWS WAF Developer Guide`_ .



========
Synopsis
========

::

    update-ip-set
  --ip-set-id <value>
  --change-token <value>
  --updates <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--ip-set-id`` (string)


  The ``IPSetId`` of the  IPSet that you want to update. ``IPSetId`` is returned by  create-ip-set and by  list-ip-sets .

  

``--change-token`` (string)


  The value returned by the most recent call to  get-change-token .

  

``--updates`` (list)


  An array of ``IPSetUpdate`` objects that you want to insert into or delete from an  IPSet . For more information, see the applicable data types:

   

   
  *  IPSetUpdate : Contains ``Action`` and ``IPSetDescriptor`` 
   
  *  IPSetDescriptor : Contains ``Type`` and ``Value`` 
   

  



Shorthand Syntax::

    Action=string,IPSetDescriptor={Type=string,Value=string} ...




JSON Syntax::

  [
    {
      "Action": "INSERT"|"DELETE",
      "IPSetDescriptor": {
        "Type": "IPV4",
        "Value": "string"
      }
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

ChangeToken -> (string)

  

  The ``change-token`` that you used to submit the ``update-ip-set`` request. You can also use this value to query the status of the request. For more information, see  get-change-token-status .

  

  



.. _AWS WAF Developer Guide: http://docs.aws.amazon.com/waf/latest/developerguide/
.. _Classless Inter-Domain Routing: https://en.wikipedia.org/wiki/Classless_Inter-Domain_Routing
