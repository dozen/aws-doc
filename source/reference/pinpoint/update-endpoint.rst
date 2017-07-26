[ :ref:`aws <cli:aws>` . :ref:`pinpoint <cli:aws pinpoint>` ]

.. _cli:aws pinpoint update-endpoint:


***************
update-endpoint
***************



===========
Description
===========

Use to update an endpoint.

========
Synopsis
========

::

    update-endpoint
  --application-id <value>
  --endpoint-id <value>
  --endpoint-request <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-id`` (string)


``--endpoint-id`` (string)


``--endpoint-request`` (structure)
Endpoint update request



Shorthand Syntax::

    Address=string,Attributes={KeyName1=string,string,KeyName2=string,string},ChannelType=string,Demographic={AppVersion=string,Locale=string,Make=string,Model=string,ModelVersion=string,Platform=string,PlatformVersion=string,Timezone=string},EffectiveDate=string,EndpointStatus=string,Location={City=string,Country=string,Latitude=double,Longitude=double,PostalCode=string,Region=string},Metrics={KeyName1=double,KeyName2=double},OptOut=string,RequestId=string,User={UserAttributes={KeyName1=[string,string],KeyName2=[string,string]},UserId=string}




JSON Syntax::

  {
    "Address": "string",
    "Attributes": {"string": ["string", ...]
      ...},
    "ChannelType": "GCM"|"APNS"|"APNS_SANDBOX"|"ADM"|"SMS"|"EMAIL",
    "Demographic": {
      "AppVersion": "string",
      "Locale": "string",
      "Make": "string",
      "Model": "string",
      "ModelVersion": "string",
      "Platform": "string",
      "PlatformVersion": "string",
      "Timezone": "string"
    },
    "EffectiveDate": "string",
    "EndpointStatus": "string",
    "Location": {
      "City": "string",
      "Country": "string",
      "Latitude": double,
      "Longitude": double,
      "PostalCode": "string",
      "Region": "string"
    },
    "Metrics": {"string": double
      ...},
    "OptOut": "string",
    "RequestId": "string",
    "User": {
      "UserAttributes": {"string": ["string", ...]
        ...},
      "UserId": "string"
    }
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

MessageBody -> (structure)

  Simple message object.

  Message -> (string)

    The error message returned from the API.

    

  RequestID -> (string)

    The unique message body ID.

    

  

