[ :ref:`aws <cli:aws>` . :ref:`glacier <cli:aws glacier>` ]

.. _cli:aws glacier get-data-retrieval-policy:


*************************
get-data-retrieval-policy
*************************



===========
Description
===========



This operation returns the current data retrieval policy for the account and region specified in the GET request. For more information about data retrieval policies, see `Amazon Glacier Data Retrieval Policies`_ .



========
Synopsis
========

::

    get-data-retrieval-policy
  --account-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--account-id`` (string)


  The ``AccountId`` value is the AWS account ID. This value must match the AWS account ID associated with the credentials used to sign the request. You can either specify an AWS account ID or optionally a single apos``-`` apos (hyphen), in which case Amazon Glacier uses the AWS account ID associated with the credentials used to sign the request. If you specify your account ID, do not include any hyphens (apos-apos) in the ID. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON account-id provided. The JSON account-id follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

The following command gets the data retrieval policy for the in-use account::

  aws glacier get-data-retrieval-policy --account-id -

Output::

  {
      "Policy": {
          "Rules": [
              {
                  "BytesPerHour": 10737418240,
                  "Strategy": "BytesPerHour"
              }
          ]
      }
  }

Amazon Glacier requires an account ID argument when performing operations, but you can use a hyphen to specify the in-use account.


======
Output
======

Policy -> (structure)

  

  Contains the returned data retrieval policy in JSON format.

  

  Rules -> (list)

    

    The policy rule. Although this is a list type, currently there must be only one rule, which contains a Strategy field and optionally a BytesPerHour field.

    

    (structure)

      

      Data retrieval policy rule.

      

      Strategy -> (string)

        

        The type of data retrieval policy to set.

         

        Valid values: BytesPerHour|FreeTier|None

        

        

      BytesPerHour -> (long)

        

        The maximum number of bytes that can be retrieved in an hour.

         

        This field is required only if the value of the Strategy field is ``BytesPerHour`` . Your PUT operation will be rejected if the Strategy field is not set to ``BytesPerHour`` and you set this field.

        

        

      

    

  



.. _Amazon Glacier Data Retrieval Policies: http://docs.aws.amazon.com/amazonglacier/latest/dev/data-retrieval-policy.html
