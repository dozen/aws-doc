[ :ref:`aws <cli:aws>` ]

.. _cli:aws support:


*******
support
*******



===========
Description
===========

 

The AWS Support API reference is intended for programmers who need detailed information about the AWS Support operations and data types. This service enables you to manage your AWS Support cases programmatically. It uses HTTP methods that return results in JSON format.

 

The AWS Support service also exposes a set of `Trusted Advisor <http://aws.amazon.com/premiumsupport/trustedadvisor/>`_ features. You can retrieve a list of checks and their descriptions, get check results, specify checks to refresh, and get the refresh status of checks. 

 

The following list describes the AWS Support case management operations:

 

 
* **Service names, issue categories, and available severity levels.** The  describe-services and  describe-severity-levels operations return AWS service names, service codes, service categories, and problem severity levels. You use these values when you call the  create-case operation.  
 
* **Case creation, case details, and case resolution.** The  create-case ,  describe-cases ,  describe-attachment , and  resolve-case operations create AWS Support cases, retrieve information about cases, and resolve cases. 
 
* **Case communication.** The  describe-communications ,  add-communication-to-case , and  add-attachments-to-set operations retrieve and add communications and attachments to AWS Support cases.  
 

 

The following list describes the operations available from the AWS Support service for Trusted Advisor:

 

 
*  describe-trusted-advisor-checks returns the list of checks that run against your AWS resources. 
 
* Using the ``checkId`` for a specific check returned by  describe-trusted-advisor-checks , you can call  describe-trusted-advisor-check-result to obtain the results for the check you specified. 
 
*  describe-trusted-advisor-check-summaries returns summarized results for one or more Trusted Advisor checks. 
 
*  refresh-trusted-advisor-check requests that Trusted Advisor rerun a specified check.  
 
*  describe-trusted-advisor-check-refresh-statuses reports the refresh status of one or more checks.  
 

 

For authentication of requests, AWS Support uses `Signature Version 4 Signing Process <http://docs.aws.amazon.com/general/latest/gr/signature-version-4.html>`_ .

 

See `About the AWS Support API <http://docs.aws.amazon.com/awssupport/latest/user/Welcome.html>`_ in the *AWS Support User Guide* for information about how to use this service to create and manage your support cases, and how to call Trusted Advisor for results of checks on your resources. 



==================
Available Commands
==================


.. toctree::
  :maxdepth: 1
  :titlesonly:

  add-attachments-to-set
  add-communication-to-case
  create-case
  describe-attachment
  describe-cases
  describe-communications
  describe-services
  describe-severity-levels
  describe-trusted-advisor-check-refresh-statuses
  describe-trusted-advisor-check-result
  describe-trusted-advisor-check-summaries
  describe-trusted-advisor-checks
  refresh-trusted-advisor-check
  resolve-case
