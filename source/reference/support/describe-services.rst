[ :ref:`aws <cli:aws>` . :ref:`support <cli:aws support>` ]

.. _cli:aws support describe-services:


*****************
describe-services
*****************



===========
Description
===========



Returns the current list of AWS services and a list of service categories that applies to each one. You then use service names and categories in your  create-case requests. Each AWS service has its own set of categories.

 

The service codes and category codes correspond to the values that are displayed in the **Service** and **Category** drop-down lists on the AWS Support Center `Create Case <https://console.aws.amazon.com/support/home#/case/create>`_ page. The values in those fields, however, do not necessarily match the service codes and categories returned by the ``describe-services`` request. Always use the service codes and categories obtained programmatically. This practice ensures that you always have the most recent set of service and category codes.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/support-2013-04-15/DescribeServices>`_


========
Synopsis
========

::

    describe-services
  [--service-code-list <value>]
  [--language <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--service-code-list`` (list)


  A JSON-formatted list of service codes available for AWS services.

  



Syntax::

  "string" "string" ...



``--language`` (string)


  The ISO 639-1 code for the language in which AWS provides support. AWS Support currently supports English ("en") and Japanese ("ja"). language parameters must be passed explicitly for operations that take them.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

services -> (list)

  

  A JSON-formatted list of AWS services.

  

  (structure)

    

    Information about an AWS service returned by the  describe-services operation. 

    

    code -> (string)

      

      The code for an AWS service returned by the  describe-services response. The ``name`` element contains the corresponding friendly name.

      

      

    name -> (string)

      

      The friendly name for an AWS service. The ``code`` element contains the corresponding code.

      

      

    categories -> (list)

      

      A list of categories that describe the type of support issue a case describes. Categories consist of a category name and a category code. Category names and codes are passed to AWS Support when you call  create-case .

      

      (structure)

        

        A JSON-formatted name/value pair that represents the category name and category code of the problem, selected from the  describe-services response for each AWS service.

        

        code -> (string)

          

          The category code for the support case.

          

          

        name -> (string)

          

          The category name for the support case.

          

          

        

      

    

  

