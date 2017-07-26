[ :ref:`aws <cli:aws>` . :ref:`support <cli:aws support>` ]

.. _cli:aws support describe-cases:


**************
describe-cases
**************



===========
Description
===========



Returns a list of cases that you specify by passing one or more case IDs. In addition, you can filter the cases by date by setting values for the ``after-time`` and ``before-time`` request parameters. You can set values for the ``no-include-resolved-cases`` and ``no-include-communications`` request parameters to control how much information is returned. 

 

Case data is available for 12 months after creation. If a case was created more than 12 months ago, a request for data might cause an error. 

 

The response returns the following in JSON format:

 

 
* One or more  CaseDetails data types. 
 
* One or more ``next-token`` values, which specify where to paginate the returned records represented by the ``CaseDetails`` objects.
 



``describe-cases`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``cases``


========
Synopsis
========

::

    describe-cases
  [--case-id-list <value>]
  [--display-id <value>]
  [--after-time <value>]
  [--before-time <value>]
  [--include-resolved-cases | --no-include-resolved-cases]
  [--language <value>]
  [--include-communications | --no-include-communications]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--case-id-list`` (list)


  A list of ID numbers of the support cases you want returned. The maximum number of cases is 100. 

  



Syntax::

  "string" "string" ...



``--display-id`` (string)


  The ID displayed for a case in the AWS Support Center user interface. 

  

``--after-time`` (string)


  The start date for a filtered date search on support case communications. Case communications are available for 12 months after creation.

  

``--before-time`` (string)


  The end date for a filtered date search on support case communications. Case communications are available for 12 months after creation.

  

``--include-resolved-cases`` | ``--no-include-resolved-cases`` (boolean)


  Specifies whether resolved support cases should be included in the  describe-cases results. The default is *false* .

  

``--language`` (string)


  The ISO 639-1 code for the language in which AWS provides support. AWS Support currently supports English ("en") and Japanese ("ja"). language parameters must be passed explicitly for operations that take them.

  

``--include-communications`` | ``--no-include-communications`` (boolean)


  Specifies whether communications should be included in the  describe-cases results. The default is *true* .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``next-token`` from a previously truncated response.

   

``--page-size`` (integer)
 

  The size of each page.

   

  

  

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``next-token`` will be provided in the output that you can use to resume pagination. This ``next-token`` response element should **not** be used directly outside of the AWS CLI.

   

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

cases -> (list)

  

  The details for the cases that match the request.

  

  (structure)

    

    A JSON-formatted object that contains the metadata for a support case. It is contained the response from a  describe-cases request. **CaseDetails** contains the following fields:

     

     
    * **CaseID.** The AWS Support case ID requested or returned in the call. The case ID is an alphanumeric string formatted as shown in this example: case-*12345678910-2013-c4c1d2bf33c5cf47* .
     
    * **CategoryCode.** The category of problem for the AWS Support case. Corresponds to the CategoryCode values returned by a call to  describe-services .
     
    * **DisplayId.** The identifier for the case on pages in the AWS Support Center.
     
    * **Language.** The ISO 639-1 code for the language in which AWS provides support. AWS Support currently supports English ("en") and Japanese ("ja"). language parameters must be passed explicitly for operations that take them.
     
    * **RecentCommunications.** One or more  Communication objects. Fields of these objects are ``Attachments`` , ``Body`` , ``CaseId`` , ``SubmittedBy`` , and ``TimeCreated`` .
     
    * **NextToken.** A resumption point for pagination.
     
    * **ServiceCode.** The identifier for the AWS service that corresponds to the service code defined in the call to  describe-services .
     
    * **SeverityCode.** The severity code assigned to the case. Contains one of the values returned by the call to  describe-severity-levels .
     
    * **Status.** The status of the case in the AWS Support Center.
     
    * **Subject.** The subject line of the case.
     
    * **SubmittedBy.** The email address of the account that submitted the case.
     
    * **TimeCreated.** The time the case was created, in ISO-8601 format.
     

    

    caseId -> (string)

      

      The AWS Support case ID requested or returned in the call. The case ID is an alphanumeric string formatted as shown in this example: case-*12345678910-2013-c4c1d2bf33c5cf47* 

      

      

    displayId -> (string)

      

      The ID displayed for the case in the AWS Support Center. This is a numeric string. 

      

      

    subject -> (string)

      

      The subject line for the case in the AWS Support Center.

      

      

    status -> (string)

      

      The status of the case. 

      

      

    serviceCode -> (string)

      

      The code for the AWS service returned by the call to  describe-services .

      

      

    categoryCode -> (string)

      

      The category of problem for the AWS Support case.

      

      

    severityCode -> (string)

      

      The code for the severity level returned by the call to  describe-severity-levels .

      

      

    submittedBy -> (string)

      

      The email address of the account that submitted the case.

      

      

    timeCreated -> (string)

      

      The time that the case was case created in the AWS Support Center. 

      

      

    recentCommunications -> (structure)

      

      The five most recent communications between you and AWS Support Center, including the IDs of any attachments to the communications. Also includes a ``nextToken`` that you can use to retrieve earlier communications.

      

      communications -> (list)

        

        The five most recent communications associated with the case.

        

        (structure)

          

          A communication associated with an AWS Support case. The communication consists of the case ID, the message body, attachment information, the account email address, and the date and time of the communication.

          

          caseId -> (string)

            

            The AWS Support case ID requested or returned in the call. The case ID is an alphanumeric string formatted as shown in this example: case-*12345678910-2013-c4c1d2bf33c5cf47* 

            

            

          body -> (string)

            

            The text of the communication between the customer and AWS Support.

            

            

          submittedBy -> (string)

            

            The email address of the account that submitted the AWS Support case. 

            

            

          timeCreated -> (string)

            

            The time the communication was created. 

            

            

          attachmentSet -> (list)

            

            Information about the attachments to the case communication. 

            

            (structure)

              

              The file name and ID of an attachment to a case communication. You can use the ID to retrieve the attachment with the  describe-attachment operation.

              

              attachmentId -> (string)

                

                The ID of the attachment.

                

                

              fileName -> (string)

                

                The file name of the attachment.

                

                

              

            

          

        

      nextToken -> (string)

        

        A resumption point for pagination.

        

        

      

    ccEmailAddresses -> (list)

      

      The email addresses that receive copies of communication about the case.

      

      (string)

        

        

      

    language -> (string)

      

      The ISO 639-1 code for the language in which AWS provides support. AWS Support currently supports English ("en") and Japanese ("ja"). language parameters must be passed explicitly for operations that take them.

      

      

    

  

nextToken -> (string)

  

  A resumption point for pagination.

  

  

