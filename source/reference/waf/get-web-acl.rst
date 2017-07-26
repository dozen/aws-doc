[ :ref:`aws <cli:aws>` . :ref:`waf <cli:aws waf>` ]

.. _cli:aws waf get-web-acl:


***********
get-web-acl
***********



===========
Description
===========



Returns the  WebACL that is specified by ``WebACLId`` .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/waf-2015-08-24/GetWebACL>`_


========
Synopsis
========

::

    get-web-acl
  --web-acl-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--web-acl-id`` (string)


  The ``WebACLId`` of the  WebACL that you want to get. ``WebACLId`` is returned by  create-web-acl and by  list-web-acls .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

WebACL -> (structure)

  

  Information about the  WebACL that you specified in the ``get-web-acl`` request. For more information, see the following topics:

   

   
  *  WebACL : Contains ``DefaultAction`` , ``MetricName`` , ``Name`` , an array of ``Rule`` objects, and ``WebACLId``   
   
  * ``DefaultAction`` (Data type is  WafAction ): Contains ``Type``   
   
  * ``Rules`` : Contains an array of ``ActivatedRule`` objects, which contain ``Action`` , ``Priority`` , and ``RuleId``   
   
  * ``Action`` : Contains ``Type``   
   

  

  WebACLId -> (string)

    

    A unique identifier for a ``WebACL`` . You use ``WebACLId`` to get information about a ``WebACL`` (see  get-web-acl ), update a ``WebACL`` (see  update-web-acl ), and delete a ``WebACL`` from AWS WAF (see  delete-web-acl ).

     

     ``WebACLId`` is returned by  create-web-acl and by  list-web-acls .

    

    

  Name -> (string)

    

    A friendly name or description of the ``WebACL`` . You can't change the name of a ``WebACL`` after you create it.

    

    

  MetricName -> (string)

    

    A friendly name or description for the metrics for this ``WebACL`` . The name can contain only alphanumeric characters (A-Z, a-z, 0-9); the name can't contain whitespace. You can't change ``MetricName`` after you create the ``WebACL`` .

    

    

  DefaultAction -> (structure)

    

    The action to perform if none of the ``Rules`` contained in the ``WebACL`` match. The action is specified by the  WafAction object.

    

    Type -> (string)

      

      Specifies how you want AWS WAF to respond to requests that match the settings in a ``Rule`` . Valid settings include the following:

       

       
      * ``ALLOW`` : AWS WAF allows requests 
       
      * ``BLOCK`` : AWS WAF blocks requests 
       
      * ``COUNT`` : AWS WAF increments a counter of the requests that match all of the conditions in the rule. AWS WAF then continues to inspect the web request based on the remaining rules in the web ACL. You can't specify ``COUNT`` for the default action for a ``WebACL`` . 
       

      

      

    

  Rules -> (list)

    

    An array that contains the action for each ``Rule`` in a ``WebACL`` , the priority of the ``Rule`` , and the ID of the ``Rule`` .

    

    (structure)

      

      The ``ActivatedRule`` object in an  update-web-acl request specifies a ``Rule`` that you want to insert or delete, the priority of the ``Rule`` in the ``WebACL`` , and the action that you want AWS WAF to take when a web request matches the ``Rule`` (``ALLOW`` , ``BLOCK`` , or ``COUNT`` ).

       

      To specify whether to insert or delete a ``Rule`` , use the ``Action`` parameter in the  WebACLUpdate data type.

      

      Priority -> (integer)

        

        Specifies the order in which the ``Rules`` in a ``WebACL`` are evaluated. Rules with a lower value for ``Priority`` are evaluated before ``Rules`` with a higher value. The value must be a unique integer. If you add multiple ``Rules`` to a ``WebACL`` , the values don't need to be consecutive.

        

        

      RuleId -> (string)

        

        The ``RuleId`` for a ``Rule`` . You use ``RuleId`` to get more information about a ``Rule`` (see  get-rule ), update a ``Rule`` (see  update-rule ), insert a ``Rule`` into a ``WebACL`` or delete a one from a ``WebACL`` (see  update-web-acl ), or delete a ``Rule`` from AWS WAF (see  delete-rule ).

         

         ``RuleId`` is returned by  create-rule and by  list-rules .

        

        

      Action -> (structure)

        

        Specifies the action that CloudFront or AWS WAF takes when a web request matches the conditions in the ``Rule`` . Valid values for ``Action`` include the following:

         

         
        * ``ALLOW`` : CloudFront responds with the requested object. 
         
        * ``BLOCK`` : CloudFront responds with an HTTP 403 (Forbidden) status code. 
         
        * ``COUNT`` : AWS WAF increments a counter of requests that match the conditions in the rule and then continues to inspect the web request based on the remaining rules in the web ACL.  
         

        

        Type -> (string)

          

          Specifies how you want AWS WAF to respond to requests that match the settings in a ``Rule`` . Valid settings include the following:

           

           
          * ``ALLOW`` : AWS WAF allows requests 
           
          * ``BLOCK`` : AWS WAF blocks requests 
           
          * ``COUNT`` : AWS WAF increments a counter of the requests that match all of the conditions in the rule. AWS WAF then continues to inspect the web request based on the remaining rules in the web ACL. You can't specify ``COUNT`` for the default action for a ``WebACL`` . 
           

          

          

        

      Type -> (string)

        

        The rule type, either ``REGULAR`` , as defined by  Rule , or ``RATE_BASED`` , as defined by  RateBasedRule . The default is REGULAR. Although this field is optional, be aware that if you try to add a RATE_BASED rule to a web ACL without setting the type, the  update-web-acl request will fail because the request tries to add a REGULAR rule with the specified ID, which does not exist. 

        

        

      

    

  

