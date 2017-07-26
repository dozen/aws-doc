[ :ref:`aws <cli:aws>` ]

.. _cli:aws meteringmarketplace:


*******************
meteringmarketplace
*******************



===========
Description
===========

 

This reference provides descriptions of the low-level AWS Marketplace Metering Service API.

 

AWS Marketplace sellers can use this API to submit usage data for custom usage dimensions.

 

 **Submitting Metering Records**  

 

 
* *meter-usage* - Submits the metering record for a Marketplace product. meter-usage is called from an EC2 instance. 
 
* *batch-meter-usage* - Submits the metering record for a set of customers. batch-meter-usage is called from a software-as-a-service (SaaS) application. 
 

 

 **Accepting New Customers**  

 

 
* *resolve-customer* - Called by a SaaS application during the registration process. When a buyer visits your website during the registration process, the buyer submits a Registration Token through the browser. The Registration Token is resolved through this API to obtain a CustomerIdentifier and Product Code. 
 



==================
Available Commands
==================


.. toctree::
  :maxdepth: 1
  :titlesonly:

  batch-meter-usage
  meter-usage
  resolve-customer
