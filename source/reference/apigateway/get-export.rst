[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway get-export:


**********
get-export
**********



===========
Description
===========



Exports a deployed version of a  RestApi in a specified format.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/apigateway-2015-07-09/GetExport>`_


========
Synopsis
========

::

    get-export
  --rest-api-id <value>
  --stage-name <value>
  --export-type <value>
  [--parameters <value>]
  [--accepts <value>]
  outfile <value>




=======
Options
=======

``--rest-api-id`` (string)


  The string identifier of the associated  RestApi .

  

``--stage-name`` (string)


  The name of the  Stage that will be exported.

  

``--export-type`` (string)


  The type of export. Currently only 'swagger' is supported.

  

``--parameters`` (map)


  A key-value map of query string parameters that specify properties of the export, depending on the requested ``exportType`` . For ``exportType``  ``swagger`` , any combination of the following parameters are supported: ``integrations`` will export the API with x-amazon-apigateway-integration extensions. ``authorizers`` will export the API with x-amazon-apigateway-authorizer extensions. ``postman`` will export the API with Postman extensions, allowing for import to the Postman tool

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``--accepts`` (string)


  The content-type of the export, for example ``application/json`` . Currently ``application/json`` and ``application/yaml`` are supported for ``exportType`` of ``swagger`` . This should be specified in the ``Accept`` header for direct API requests.

  

``outfile`` (string)
Filename where the content will be saved



========
Examples
========

**To get the JSON Swagger template for a stage**

Command::

  aws apigateway get-export --rest-api-id a1b2c3d4e5 --stage-name dev --export-type swagger /path/to/filename.json

**To get the JSON Swagger template + API Gateway Extentions for a stage**

Command::

  aws apigateway get-export --parameters extensions='integrations' --rest-api-id a1b2c3d4e5 --stage-name dev --export-type swagger /path/to/filename.json

**To get the JSON Swagger template + Postman Extensions for a stage**

Command::

  aws apigateway get-export --parameters extensions='postman' --rest-api-id a1b2c3d4e5 --stage-name dev --export-type swagger /path/to/filename.json



======
Output
======

contentType -> (string)

  

  The content-type header value in the HTTP response. This will correspond to a valid 'accept' type in the request.

  

  

contentDisposition -> (string)

  

  The content-disposition header value in the HTTP response.

  

  

body -> (blob)

  

  The binary blob response to  get-export , which contains the export.

  

  

