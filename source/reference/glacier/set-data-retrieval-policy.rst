[ :ref:`aws <cli:aws>` . :ref:`glacier <cli:aws glacier>` ]

.. _cli:aws glacier set-data-retrieval-policy:


*************************
set-data-retrieval-policy
*************************



===========
Description
===========



This operation sets and then enacts a data retrieval policy in the region specified in the PUT request. You can set one policy per region for an AWS account. The policy is enacted within a few minutes of a successful PUT operation. 

 

The set policy operation does not affect retrieval jobs that were in progress before the policy was enacted. For more information about data retrieval policies, see `Amazon Glacier Data Retrieval Policies`_ . 



========
Synopsis
========

::

    set-data-retrieval-policy
  --account-id <value>
  [--policy <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--account-id`` (string)


  The ``AccountId`` value is the AWS account ID. This value must match the AWS account ID associated with the credentials used to sign the request. You can either specify an AWS account ID or optionally a single apos``-`` apos (hyphen), in which case Amazon Glacier uses the AWS account ID associated with the credentials used to sign the request. If you specify your account ID, do not include any hyphens (apos-apos) in the ID.

  

``--policy`` (structure)


  The data retrieval policy in JSON format.

  



Shorthand Syntax::

    Rules=[{Strategy=string,BytesPerHour=long},{Strategy=string,BytesPerHour=long}]




JSON Syntax::

  {
    "Rules": [
      {
        "Strategy": "string",
        "BytesPerHour": long
      }
      ...
    ]
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON account-id provided. The JSON account-id follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

The following command configures a data retrieval policy for the in-use account::

  aws glacier set-data-retrieval-policy --account-id - --policy file://data-retrieval-policy.json

``data-retrieval-policy.json`` is a JSON file in the current folder that specifies a data retrieval policy::

  {
    "Rules":[
       {
           "Strategy":"BytesPerHour",
           "BytesPerHour":10737418240
        }
     ]
  }

Amazon Glacier requires an account ID argument when performing operations, but you can use a hyphen to specify the in-use account.

The following command sets the data retrieval policy to ``FreeTier`` using inline JSON::

  aws glacier set-data-retrieval-policy --account-id - --policy '{"Rules":[{"Strategy":"FreeTier"}]}'

See `Set Data Retrieval Policy`_ in the *Amazon Glacier API Reference* for details on the policy format.

.. _`Set Data Retrieval Policy`: http://docs.aws.amazon.com/amazonglacier/latest/dev/api-SetDataRetrievalPolicy.html


======
Output
======

None

.. _Amazon Glacier Data Retrieval Policies: http://docs.aws.amazon.com/amazonglacier/latest/dev/data-retrieval-policy.html
