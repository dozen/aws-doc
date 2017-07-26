[ :ref:`aws <cli:aws>` . :ref:`ecr <cli:aws ecr>` ]

.. _cli:aws ecr get-authorization-token:


***********************
get-authorization-token
***********************



===========
Description
===========



Retrieves a token that is valid for a specified registry for 12 hours. This command allows you to use the ``docker`` CLI to push and pull images with Amazon ECR. If you do not specify a registry, the default registry is assumed.

 

The ``authorizationToken`` returned for each registry specified is a base64 encoded string that can be decoded and used in a ``docker login`` command to authenticate to a registry. The AWS CLI offers an ``aws ecr get-login`` command that simplifies the login process.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ecr-2015-09-21/GetAuthorizationToken>`_


========
Synopsis
========

::

    get-authorization-token
  [--registry-ids <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--registry-ids`` (list)


  A list of AWS account IDs that are associated with the registries for which to get authorization tokens. If you do not specify a registry, the default registry is assumed.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To get an authorization token for your default registry**

This example command gets an authorization token for your default registry.

Command::

  aws ecr get-authorization-token

Output::

  {
      "authorizationData": [
          {
              "authorizationToken": "QVdTOkN...",
              "expiresAt": 1448875853.241,
              "proxyEndpoint": "https://<aws_account_id>.dkr.ecr.us-west-2.amazonaws.com"
          }
      ]
  }


**To get the decoded password for your default registry**

This example command gets an authorization token for your default registry and
returns the decoded password for you to use in a ``docker login`` command.

.. note::

    Mac OSX users should use the ``-D`` option to ``base64`` to decode the
    token data.

Command::

  aws ecr get-authorization-token --output text \
  --query 'authorizationData[].authorizationToken' \
  | base64 -D | cut -d: -f2


**To `docker login` with your decoded password**

This example command uses your decoded password to add authentication
information to your Docker installation by using the ``docker login`` command.
The user name is ``AWS``, and you can use any email you want (Amazon ECR does
nothing with this information, but ``docker login`` required the email field).

.. note::

    The final argument is the ``proxyEndpoint`` returned from
    ``get-authorization-token`` without the ``https://`` prefix.

Command::

  docker login -u AWS -p <my_decoded_password> -e <any_email_address> <aws_account_id>.dkr.ecr.us-west-2.amazonaws.com

Output::

  WARNING: login credentials saved in $HOME/.docker/config.json
  Login Succeeded


======
Output
======

authorizationData -> (list)

  

  A list of authorization token data objects that correspond to the ``registryIds`` values in the request.

  

  (structure)

    

    An object representing authorization data for an Amazon ECR registry.

    

    authorizationToken -> (string)

      

      A base64-encoded string that contains authorization data for the specified Amazon ECR registry. When the string is decoded, it is presented in the format ``user:password`` for private registry authentication using ``docker login`` .

      

      

    expiresAt -> (timestamp)

      

      The Unix time in seconds and milliseconds when the authorization token expires. Authorization tokens are valid for 12 hours.

      

      

    proxyEndpoint -> (string)

      

      The registry URL to use for this authorization token in a ``docker login`` command. The Amazon ECR registry URL format is ``https://aws_account_id.dkr.ecr.region.amazonaws.com`` . For example, ``https://012345678910.dkr.ecr.us-east-1.amazonaws.com`` .. 

      

      

    

  

