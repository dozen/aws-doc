[ :ref:`aws <cli:aws>` . :ref:`waf-regional <cli:aws waf-regional>` ]

.. _cli:aws waf-regional create-web-acl:


**************
create-web-acl
**************



===========
Description
===========



Creates a ``WebACL`` , which contains the ``Rules`` that identify the CloudFront web requests that you want to allow, block, or count. AWS WAF evaluates ``Rules`` in order based on the value of ``Priority`` for each ``Rule`` .

 

You also specify a default action, either ``ALLOW`` or ``BLOCK`` . If a web request doesn't match any of the ``Rules`` in a ``WebACL`` , AWS WAF responds to the request with the default action. 

 

To create and configure a ``WebACL`` , perform the following steps:

 

 
* Create and update the ``ByteMatchSet`` objects and other predicates that you want to include in ``Rules`` . For more information, see  create-byte-match-set ,  update-byte-match-set ,  create-ip-set ,  update-ip-set ,  create-sql-injection-match-set , and  update-sql-injection-match-set . 
 
* Create and update the ``Rules`` that you want to include in the ``WebACL`` . For more information, see  create-rule and  update-rule . 
 
* Use  get-change-token to get the change token that you provide in the ``change-token`` parameter of a ``create-web-acl`` request. 
 
* Submit a ``create-web-acl`` request. 
 
* Use ``get-change-token`` to get the change token that you provide in the ``change-token`` parameter of an  update-web-acl request. 
 
* Submit an  update-web-acl request to specify the ``Rules`` that you want to include in the ``WebACL`` , to specify the default action, and to associate the ``WebACL`` with a CloudFront distribution. 
 

 

For more information about how to use the AWS WAF API, see the `AWS WAF Developer Guide <http://docs.aws.amazon.com/waf/latest/developerguide/>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/waf-regional-2016-11-28/CreateWebACL>`_


========
Synopsis
========

::

    create-web-acl
  --name <value>
  --metric-name <value>
  --default-action <value>
  --change-token <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  A friendly name or description of the  WebACL . You can't change ``Name`` after you create the ``WebACL`` .

  

``--metric-name`` (string)


  A friendly name or description for the metrics for this ``WebACL`` . The name can contain only alphanumeric characters (A-Z, a-z, 0-9); the name can't contain whitespace. You can't change ``metric-name`` after you create the ``WebACL`` .

  

``--default-action`` (structure)


  The action that you want AWS WAF to take when a request doesn't match the criteria specified in any of the ``Rule`` objects that are associated with the ``WebACL`` .

  



Shorthand Syntax::

    Type=string




JSON Syntax::

  {
    "Type": "BLOCK"|"ALLOW"|"COUNT"
  }



``--change-token`` (string)


  The value returned by the most recent call to  get-change-token .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

WebACL -> (structure)

  

  The  WebACL returned in the ``create-web-acl`` response.

  

  WebACLId -> (string)

    

    A unique identifier for a ``WebACL`` . You use ``WebACLId`` to get information about a ``WebACL`` (see  get-web-acl ), update a ``WebACL`` (see  update-web-acl ), and delete a ``WebACL`` from AWS WAF (see  delete-web-acl ).

     

     ``WebACLId`` is returned by  create-web-acl and by  list-web-acls .

    

    

  Name -> (string)

    

    A friendly name or description of the ``WebACL`` . You can't change the name of a ``WebACL`` after you create it.

    

    

  MetricName -> (string)

    

    A friendly name or description for the metrics for this ``WebACL`` . The name can contain only alphanumeric characters (A-Z, a-z, 0-9); the name can't contain whitespace. You can't change ``metric-name`` after you create the ``WebACL`` .

    

    

  DefaultAction -> (structure)

    

    The action to perform if none of the ``Rules`` contained in the ``WebACL`` match. The action is specified by the  default-action object.

    

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

        

        

      

    

  

ChangeToken -> (string)

  

  The ``change-token`` that you used to submit the ``create-web-acl`` request. You can also use this value to query the status of the request. For more information, see  get-change-token-status .

  

  

