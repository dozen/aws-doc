[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway update-base-path-mapping:


************************
update-base-path-mapping
************************



===========
Description
===========



Changes information about the  BasePathMapping resource.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/apigateway-2015-07-09/UpdateBasePathMapping>`_


========
Synopsis
========

::

    update-base-path-mapping
  --domain-name <value>
  --base-path <value>
  [--patch-operations <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--domain-name`` (string)


  The domain name of the  BasePathMapping resource to change.

  

``--base-path`` (string)


  The base path of the  BasePathMapping resource to change.

  

``--patch-operations`` (list)


  A list of update operations to be applied to the specified resource and in the order specified in this list.

  



Shorthand Syntax::

    op=string,path=string,value=string,from=string ...




JSON Syntax::

  [
    {
      "op": "add"|"remove"|"replace"|"move"|"copy"|"test",
      "path": "string",
      "value": "string",
      "from": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To change the base path for a custom domain name**

Command::

  aws apigateway update-base-path-mapping --domain-name api.domain.tld --base-path prod --patch-operations op='replace',path='/basePath',value='v1'

Output::

  {
      "basePath": "v1", 
      "restApiId": "1234123412", 
      "stage": "api"
  }


======
Output
======

basePath -> (string)

  

  The base path name that callers of the API must provide as part of the URL after the domain name.

  

  

restApiId -> (string)

  

  The string identifier of the associated  RestApi .

  

  

stage -> (string)

  

  The name of the associated stage.

  

  

