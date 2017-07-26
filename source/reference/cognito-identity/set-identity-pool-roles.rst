[ :ref:`aws <cli:aws>` . :ref:`cognito-identity <cli:aws cognito-identity>` ]

.. _cli:aws cognito-identity set-identity-pool-roles:


***********************
set-identity-pool-roles
***********************



===========
Description
===========



Sets the roles for an identity pool. These roles are used when making calls to  get-credentials-for-identity action.

 

You must use AWS Developer credentials to call this API.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cognito-identity-2014-06-30/SetIdentityPoolRoles>`_


========
Synopsis
========

::

    set-identity-pool-roles
  --identity-pool-id <value>
  --roles <value>
  [--role-mappings <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--identity-pool-id`` (string)


  An identity pool ID in the format REGION:GUID.

  

``--roles`` (map)


  The map of roles associated with this pool. For a given role, the key will be either "authenticated" or "unauthenticated" and the value will be the Role ARN.

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``--role-mappings`` (map)


  How users for a specific identity provider are to mapped to roles. This is a string to  RoleMapping object map. The string identifies the identity provider, for example, "graph.facebook.com" or "cognito-idp-east-1.amazonaws.com/us-east-1_abcdefghi:app_client_id".

   

  Up to 25 rules can be specified per identity provider.

  



JSON Syntax::

  {"string": {
        "Type": "Token"|"Rules",
        "AmbiguousRoleResolution": "AuthenticatedRole"|"Deny",
        "RulesConfiguration": {
          "Rules": [
            {
              "Claim": "string",
              "MatchType": "Equals"|"Contains"|"StartsWith"|"NotEqual",
              "Value": "string",
              "RoleARN": "string"
            }
            ...
          ]
        }
      }
    ...}



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None