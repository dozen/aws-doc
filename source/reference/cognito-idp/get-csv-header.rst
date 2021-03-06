[ :ref:`aws <cli:aws>` . :ref:`cognito-idp <cli:aws cognito-idp>` ]

.. _cli:aws cognito-idp get-csv-header:


**************
get-csv-header
**************



===========
Description
===========



Gets the header information for the .csv file to be used as input for the user import job.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cognito-idp-2016-04-18/GetCSVHeader>`_


========
Synopsis
========

::

    get-csv-header
  --user-pool-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--user-pool-id`` (string)


  The user pool ID for the user pool that the users are to be imported into.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

UserPoolId -> (string)

  

  The user pool ID for the user pool that the users are to be imported into.

  

  

CSVHeader -> (list)

  

  The header information for the .csv file for the user import job.

  

  (string)

    

    

  

