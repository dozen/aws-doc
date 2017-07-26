[ :ref:`aws <cli:aws>` . :ref:`waf-regional <cli:aws waf-regional>` ]

.. _cli:aws waf-regional update-ip-set:


*************
update-ip-set
*************



===========
Description
===========



Inserts or deletes  IPSetDescriptor objects in an ``IPSet`` . For each ``IPSetDescriptor`` object, you specify the following values: 

 

 
* Whether to insert or delete the object from the array. If you want to change an ``IPSetDescriptor`` object, you delete the existing object and add a new one. 
 
* The IP address version, ``IPv4`` or ``IPv6`` .  
 
* The IP address in CIDR notation, for example, ``192.0.2.0/24`` (for the range of IP addresses from ``192.0.2.0`` to ``192.0.2.255`` ) or ``192.0.2.44/32`` (for the individual IP address ``192.0.2.44`` ).  
 

 

AWS WAF supports /8, /16, /24, and /32 IP address ranges for IPv4, and /24, /32, /48, /56, /64 and /128 for IPv6. For more information about CIDR notation, see the Wikipedia entry `Classless Inter-Domain Routing <https://en.wikipedia.org/wiki/Classless_Inter-Domain_Routing>`_ .

 

IPv6 addresses can be represented using any of the following formats:

 

 
* 1111:0000:0000:0000:0000:0000:0000:0111/128 
 
* 1111:0:0:0:0:0:0:0111/128 
 
* 1111::0111/128 
 
* 1111::111/128 
 

 

You use an ``IPSet`` to specify which web requests you want to allow or block based on the IP addresses that the requests originated from. For example, if you're receiving a lot of requests from one or a small number of IP addresses and you want to block the requests, you can create an ``IPSet`` that specifies those IP addresses, and then configure AWS WAF to block the requests. 

 

To create and configure an ``IPSet`` , perform the following steps:

 

 
* Submit a  create-ip-set request. 
 
* Use  get-change-token to get the change token that you provide in the ``change-token`` parameter of an  update-ip-set request. 
 
* Submit an ``update-ip-set`` request to specify the IP addresses that you want AWS WAF to watch for. 
 

 

When you update an ``IPSet`` , you specify the IP addresses that you want to add and/or the IP addresses that you want to delete. If you want to change an IP address, you delete the existing IP address and add the new one.

 

For more information about how to use the AWS WAF API to allow or block HTTP requests, see the `AWS WAF Developer Guide <http://docs.aws.amazon.com/waf/latest/developerguide/>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/waf-regional-2016-11-28/UpdateIPSet>`_


========
Synopsis
========

::

    update-ip-set
  --ip-set-id <value>
  --change-token <value>
  --updates <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




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
        "Type": "IPV4"|"IPV6",
        "Value": "string"
      }
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ChangeToken -> (string)

  

  The ``change-token`` that you used to submit the ``update-ip-set`` request. You can also use this value to query the status of the request. For more information, see  get-change-token-status .

  

  

