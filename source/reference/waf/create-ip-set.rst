[ :ref:`aws <cli:aws>` . :ref:`waf <cli:aws waf>` ]

.. _cli:aws waf create-ip-set:


*************
create-ip-set
*************



===========
Description
===========



Creates an  IPSet , which you use to specify which web requests you want to allow or block based on the IP addresses that the requests originate from. For example, if you're receiving a lot of requests from one or more individual IP addresses or one or more ranges of IP addresses and you want to block the requests, you can create an ``IPSet`` that contains those IP addresses and then configure AWS WAF to block the requests. 

 

To create and configure an ``IPSet`` , perform the following steps:

 

 
* Use  get-change-token to get the change token that you provide in the ``change-token`` parameter of a ``create-ip-set`` request. 
 
* Submit a ``create-ip-set`` request. 
 
* Use ``get-change-token`` to get the change token that you provide in the ``change-token`` parameter of an  update-ip-set request. 
 
* Submit an ``update-ip-set`` request to specify the IP addresses that you want AWS WAF to watch for. 
 

 

For more information about how to use the AWS WAF API to allow or block HTTP requests, see the `AWS WAF Developer Guide <http://docs.aws.amazon.com/waf/latest/developerguide/>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/waf-2015-08-24/CreateIPSet>`_


========
Synopsis
========

::

    create-ip-set
  --name <value>
  --change-token <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  A friendly name or description of the  IPSet . You can't change ``Name`` after you create the ``IPSet`` .

  

``--change-token`` (string)


  The value returned by the most recent call to  get-change-token .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

IPSet -> (structure)

  

  The  IPSet returned in the ``create-ip-set`` response.

  

  IPSetId -> (string)

    

    The ``IPSetId`` for an ``IPSet`` . You use ``IPSetId`` to get information about an ``IPSet`` (see  get-ip-set ), update an ``IPSet`` (see  update-ip-set ), insert an ``IPSet`` into a ``Rule`` or delete one from a ``Rule`` (see  update-rule ), and delete an ``IPSet`` from AWS WAF (see  delete-ip-set ).

     

     ``IPSetId`` is returned by  create-ip-set and by  list-ip-sets .

    

    

  Name -> (string)

    

    A friendly name or description of the  IPSet . You can't change the name of an ``IPSet`` after you create it.

    

    

  IPSetDescriptors -> (list)

    

    The IP address type (``IPV4`` or ``IPV6`` ) and the IP address range (in CIDR notation) that web requests originate from. If the ``WebACL`` is associated with a CloudFront distribution and the viewer did not use an HTTP proxy or a load balancer to send the request, this is the value of the c-ip field in the CloudFront access logs.

    

    (structure)

      

      Specifies the IP address type (``IPV4`` or ``IPV6`` ) and the IP address range (in CIDR format) that web requests originate from.

      

      Type -> (string)

        

        Specify ``IPV4`` or ``IPV6`` .

        

        

      Value -> (string)

        

        Specify an IPv4 address by using CIDR notation. For example:

         

         
        * To configure AWS WAF to allow, block, or count requests that originated from the IP address 192.0.2.44, specify ``192.0.2.44/32`` . 
         
        * To configure AWS WAF to allow, block, or count requests that originated from IP addresses from 192.0.2.0 to 192.0.2.255, specify ``192.0.2.0/24`` . 
         

         

        For more information about CIDR notation, see the Wikipedia entry `Classless Inter-Domain Routing <https://en.wikipedia.org/wiki/Classless_Inter-Domain_Routing>`_ .

         

        Specify an IPv6 address by using CIDR notation. For example:

         

         
        * To configure AWS WAF to allow, block, or count requests that originated from the IP address 1111:0000:0000:0000:0000:0000:0000:0111, specify ``1111:0000:0000:0000:0000:0000:0000:0111/128`` . 
         
        * To configure AWS WAF to allow, block, or count requests that originated from IP addresses 1111:0000:0000:0000:0000:0000:0000:0000 to 1111:0000:0000:0000:ffff:ffff:ffff:ffff, specify ``1111:0000:0000:0000:0000:0000:0000:0000/64`` . 
         

        

        

      

    

  

ChangeToken -> (string)

  

  The ``change-token`` that you used to submit the ``create-ip-set`` request. You can also use this value to query the status of the request. For more information, see  get-change-token-status .

  

  

