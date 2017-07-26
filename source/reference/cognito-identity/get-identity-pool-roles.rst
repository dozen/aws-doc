[ :ref:`aws <cli:aws>` . :ref:`cognito-identity <cli:aws cognito-identity>` ]

.. _cli:aws cognito-identity get-identity-pool-roles:


***********************
get-identity-pool-roles
***********************



===========
Description
===========



Gets the roles for an identity pool.

 

You must use AWS Developer credentials to call this API.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cognito-identity-2014-06-30/GetIdentityPoolRoles>`_


========
Synopsis
========

::

    get-identity-pool-roles
  --identity-pool-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--identity-pool-id`` (string)


  An identity pool ID in the format REGION:GUID.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

IdentityPoolId -> (string)

  

  An identity pool ID in the format REGION:GUID.

  

  

Roles -> (map)

  

  The map of roles associated with this pool. Currently only authenticated and unauthenticated roles are supported.

  

  key -> (string)

    

    

  value -> (string)

    

    

  

RoleMappings -> (map)

  

  How users for a specific identity provider are to mapped to roles. This is a String-to- RoleMapping object map. The string identifies the identity provider, for example, "graph.facebook.com" or "cognito-idp-east-1.amazonaws.com/us-east-1_abcdefghi:app_client_id".

  

  key -> (string)

    

    

  value -> (structure)

    

    A role mapping.

    

    Type -> (string)

      

      The role mapping type. Token will use ``cognito:roles`` and ``cognito:preferred_role`` claims from the Cognito identity provider token to map groups to roles. Rules will attempt to match claims from the token to map to a role.

      

      

    AmbiguousRoleResolution -> (string)

      

      If you specify Token or Rules as the ``Type`` , ``AmbiguousRoleResolution`` is required.

       

      Specifies the action to be taken if either no rules match the claim value for the ``Rules`` type, or there is no ``cognito:preferred_role`` claim and there are multiple ``cognito:roles`` matches for the ``Token`` type.

      

      

    RulesConfiguration -> (structure)

      

      The rules to be used for mapping users to roles.

       

      If you specify Rules as the role mapping type, ``RulesConfiguration`` is required.

      

      Rules -> (list)

        

        An array of rules. You can specify up to 25 rules per identity provider.

         

        Rules are evaluated in order. The first one to match specifies the role.

        

        (structure)

          

          A rule that maps a claim name, a claim value, and a match type to a role ARN.

          

          Claim -> (string)

            

            The claim name that must be present in the token, for example, "isAdmin" or "paid".

            

            

          MatchType -> (string)

            

            The match condition that specifies how closely the claim value in the IdP token must match ``Value`` .

            

            

          Value -> (string)

            

            A brief string that the claim must match, for example, "paid" or "yes".

            

            

          RoleARN -> (string)

            

            The role ARN.

            

            

          

        

      

    

  

