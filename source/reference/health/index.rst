[ :ref:`aws <cli:aws>` ]

.. _cli:aws health:


******
health
******



===========
Description
===========

 

The AWS Health API provides programmatic access to the AWS Health information that is presented in the `AWS Personal Health Dashboard <https://phd.aws.amazon.com/phd/home#/>`_ . You can get information about events that affect your AWS resources:

 

 
*  describe-events : Summary information about events. 
 
*  describe-event-details : Detailed information about one or more events. 
 
*  describe-affected-entities : Information about AWS resources that are affected by one or more events. 
 

 

In addition, these operations provide information about event types and summary counts of events or affected entities:

 

 
*  describe-event-types : Information about the kinds of events that AWS Health tracks. 
 
*  describe-event-aggregates : A count of the number of events that meet specified criteria. 
 
*  describe-entity-aggregates : A count of the number of affected entities that meet specified criteria. 
 

 

The Health API requires a Business or Enterprise support plan from `AWS Support <http://aws.amazon.com/premiumsupport/>`_ . Calling the Health API from an account that does not have a Business or Enterprise support plan causes a ``SubscriptionRequiredException`` . 

 

For authentication of requests, AWS Health uses the `Signature Version 4 Signing Process <http://docs.aws.amazon.com/general/latest/gr/signature-version-4.html>`_ .

 

See the `AWS Health User Guide <http://docs.aws.amazon.com/health/latest/ug/what-is-aws-health.html>`_ for information about how to use the API.

 

 **Service Endpoint**  

 

The HTTP endpoint for the AWS Health API is:

 

 
* https://health.us-east-1.amazonaws.com  
 



==================
Available Commands
==================


.. toctree::
  :maxdepth: 1
  :titlesonly:

  describe-affected-entities
  describe-entity-aggregates
  describe-event-aggregates
  describe-event-details
  describe-event-types
  describe-events
