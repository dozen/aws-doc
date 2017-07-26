[ :ref:`aws <cli:aws>` . :ref:`waf <cli:aws waf>` ]

.. _cli:aws waf get-ip-set:


**********
get-ip-set
**********



===========
Description
===========



Returns the  IPSet that is specified by ``IPSetId`` .



========
Synopsis
========

::

    get-ip-set
  --ip-set-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--ip-set-id`` (string)


  The ``IPSetId`` of the  IPSet that you want to get. ``IPSetId`` is returned by  create-ip-set and by  list-ip-sets .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

IPSet -> (structure)

  

  Information about the  IPSet that you specified in the ``get-ip-set`` request. For more information, see the following topics:

   

   
  *  IPSet : Contains ``IPSetDescriptors`` , ``IPSetId`` , and ``Name`` 
   
  * ``IPSetDescriptors`` : Contains an array of  IPSetDescriptor objects. Each ``IPSetDescriptor`` object contains ``Type`` and ``Value`` 
   

  

  IPSetId -> (string)

    

    The ``IPSetId`` for an ``IPSet`` . You use ``IPSetId`` to get information about an ``IPSet`` (see  get-ip-set ), update an ``IPSet`` (see  update-ip-set ), insert an ``IPSet`` into a ``Rule`` or delete one from a ``Rule`` (see  update-rule ), and delete an ``IPSet`` from AWS WAF (see  delete-ip-set ).

     

    ``IPSetId`` is returned by  create-ip-set and by  list-ip-sets .

    

    

  Name -> (string)

    

    A friendly name or description of the  IPSet . You can't change the name of an ``IPSet`` after you create it.

    

    

  IPSetDescriptors -> (list)

    

    The IP address type (``IPV4`` ) and the IP address range (in CIDR notation) that web requests originate from. If the ``WebACL`` is associated with a CloudFront distribution, this is the value of one of the following fields in CloudFront access logs:

     

     
    * ``c-ip`` , if the viewer did not use an HTTP proxy or a load balancer to send the request
     
    * ``x-forwarded-for`` , if the viewer did use an HTTP proxy or a load balancer to send the request
     

    

    (structure)

      

      Specifies the IP address type (``IPV4`` ) and the IP address range (in CIDR format) that web requests originate from.

      

      Type -> (string)

        

        Specify ``IPV4`` .

        

        

      Value -> (string)

        

        Specify an IPv4 address by using CIDR notation. For example:

         

         
        * To configure AWS WAF to allow, block, or count requests that originated from the IP address 192.0.2.44, specify ``192.0.2.44/32`` .
         
        * To configure AWS WAF to allow, block, or count requests that originated from IP addresses from 192.0.2.0 to 192.0.2.255, specify ``192.0.2.0/24`` .
         

         

        AWS WAF supports only /8, /16, /24, and /32 IP addresses.

         

        For more information about CIDR notation, see the Wikipedia entry `Classless Inter-Domain Routing`_ .

        

        

      

    

  



.. _Classless Inter-Domain Routing: https://en.wikipedia.org/wiki/Classless_Inter-Domain_Routing
