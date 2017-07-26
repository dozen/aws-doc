[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway get-sdk:


*******
get-sdk
*******



===========
Description
===========



Generates a client SDK for a  RestApi and  Stage .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/apigateway-2015-07-09/GetSdk>`_


========
Synopsis
========

::

    get-sdk
  --rest-api-id <value>
  --stage-name <value>
  --sdk-type <value>
  [--parameters <value>]
  outfile <value>




=======
Options
=======

``--rest-api-id`` (string)


  The string identifier of the associated  RestApi .

  

``--stage-name`` (string)


  The name of the  Stage that the SDK will use.

  

``--sdk-type`` (string)


  The language for the generated SDK. Currently ``javascript`` , ``android`` , and ``objectivec`` (for iOS) are supported.

  

``--parameters`` (map)


  A key-value map of query string parameters that specify properties of the SDK, depending on the requested ``sdkType`` . For ``sdkType`` of ``objectivec`` , a parameter named ``classPrefix`` is required. For ``sdkType`` of ``android`` , parameters named ``groupId`` , ``artifactId`` , ``artifactVersion`` , and ``invokerPackage`` are required.

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``outfile`` (string)
Filename where the content will be saved



========
Examples
========

**To get the Android SDK for a REST API stage**

Command::

  aws apigateway get-sdk --rest-api-id 1234123412 --stage-name dev --sdk-type android --parameters groupId='com.mycompany',invokerPackage='com.mycompany.clientsdk',artifactId='Mycompany-client',artifactVersion='1.0.0' /path/to/android_sdk.zip

Output::

  {
      "contentType": "application/octet-stream", 
      "contentDisposition": "attachment; filename=\"android_2016-02-22_23-52Z.zip\""
  }

**To get the IOS SDK for a REST API stage**

Command::

  aws apigateway get-sdk --rest-api-id 1234123412 --stage-name dev --sdk-type objectivec --parameters classPrefix='myprefix' /path/to/iOS_sdk.zip

Output::

  {
      "contentType": "application/octet-stream", 
      "contentDisposition": "attachment; filename=\"objectivec_2016-02-22_23-52Z.zip\""
  }

**To get the Javascript SDK for a REST API stage**

Command::

  aws apigateway get-sdk --rest-api-id 1234123412 --stage-name dev --sdk-type javascript /path/to/javascript_sdk.zip

Output::

  {
      "contentType": "application/octet-stream", 
      "contentDisposition": "attachment; filename=\"javascript_2016-02-22_23-52Z.zip\""
  }



======
Output
======

contentType -> (string)

  

  The content-type header value in the HTTP response.

  

  

contentDisposition -> (string)

  

  The content-disposition header value in the HTTP response.

  

  

body -> (blob)

  

  The binary blob response to  get-sdk , which contains the generated SDK.

  

  

