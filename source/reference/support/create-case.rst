[ :ref:`aws <cli:aws>` . :ref:`support <cli:aws support>` ]

.. _cli:aws support create-case:


***********
create-case
***********



===========
Description
===========



Creates a new case in the AWS Support Center. This operation is modeled on the behavior of the AWS Support Center `Create Case <https://console.aws.amazon.com/support/home#/case/create>`_ page. Its parameters require you to specify the following information: 

 

 
* **issueType.** The type of issue for the case. You can specify either "customer-service" or "technical." If you do not indicate a value, the default is "technical."  
 
* **serviceCode.** The code for an AWS service. You obtain the ``serviceCode`` by calling  describe-services .  
 
* **categoryCode.** The category for the service defined for the ``serviceCode`` value. You also obtain the category code for a service by calling  describe-services . Each AWS service defines its own set of category codes.  
 
* **severityCode.** A value that indicates the urgency of the case, which in turn determines the response time according to your service level agreement with AWS Support. You obtain the severity-code by calling  describe-severity-levels . 
 
* **subject.** The **subject** field on the AWS Support Center `Create Case <https://console.aws.amazon.com/support/home#/case/create>`_ page. 
 
* **communicationBody.** The **Description** field on the AWS Support Center `Create Case <https://console.aws.amazon.com/support/home#/case/create>`_ page. 
 
* **attachmentSetId.** The ID of a set of attachments that has been created by using  add-attachments-to-set . 
 
* **language.** The human language in which AWS Support handles the case. English and Japanese are currently supported. 
 
* **ccEmailAddresses.** The AWS Support Center **CC** field on the `Create Case <https://console.aws.amazon.com/support/home#/case/create>`_ page. You can list email addresses to be copied on any correspondence about the case. The account that opens the case is already identified by passing the AWS Credentials in the HTTP POST method or in a method or function call from one of the programming languages supported by an `AWS SDK <http://aws.amazon.com/tools/>`_ .  
 

 

.. note::

   

  To add additional communication or attachments to an existing case, use  add-communication-to-case .

   

 

A successful  create-case request returns an AWS Support case number. Case numbers are used by the  describe-cases operation to retrieve existing AWS Support cases. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/support-2013-04-15/CreateCase>`_


========
Synopsis
========

::

    create-case
  --subject <value>
  [--service-code <value>]
  [--severity-code <value>]
  [--category-code <value>]
  --communication-body <value>
  [--cc-email-addresses <value>]
  [--language <value>]
  [--issue-type <value>]
  [--attachment-set-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--subject`` (string)


  The title of the AWS Support case.

  

``--service-code`` (string)


  The code for the AWS service returned by the call to  describe-services .

  

``--severity-code`` (string)


  The code for the severity level returned by the call to  describe-severity-levels .

   

  .. note::

     

    The availability of severity levels depends on each customer's support subscription. In other words, your subscription may not necessarily require the urgent level of response time.

     

  

``--category-code`` (string)


  The category of problem for the AWS Support case.

  

``--communication-body`` (string)


  The communication body text when you create an AWS Support case by calling  create-case .

  

``--cc-email-addresses`` (list)


  A list of email addresses that AWS Support copies on case correspondence.

  



Syntax::

  "string" "string" ...



``--language`` (string)


  The ISO 639-1 code for the language in which AWS provides support. AWS Support currently supports English ("en") and Japanese ("ja"). language parameters must be passed explicitly for operations that take them.

  

``--issue-type`` (string)


  The type of issue for the case. You can specify either "customer-service" or "technical." If you do not indicate a value, the default is "technical."

  

``--attachment-set-id`` (string)


  The ID of a set of one or more attachments for the case. Create the set by using  add-attachments-to-set .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

caseId -> (string)

  

  The AWS Support case ID requested or returned in the call. The case ID is an alphanumeric string formatted as shown in this example: case-*12345678910-2013-c4c1d2bf33c5cf47*  

  

  

