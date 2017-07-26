[ :ref:`aws <cli:aws>` . :ref:`codebuild <cli:aws codebuild>` ]

.. _cli:aws codebuild list-curated-environment-images:


*******************************
list-curated-environment-images
*******************************



===========
Description
===========



Gets information about Docker images that are managed by AWS CodeBuild.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codebuild-2016-10-06/ListCuratedEnvironmentImages>`_


========
Synopsis
========

::

    list-curated-environment-images
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

platforms -> (list)

  

  Information about supported platforms for Docker images that are managed by AWS CodeBuild.

  

  (structure)

    

    A set of Docker images that are related by platform and are managed by AWS CodeBuild.

    

    platform -> (string)

      

      The platform's name.

      

      

    languages -> (list)

      

      The list of programming languages that are available for the specified platform.

      

      (structure)

        

        A set of Docker images that are related by programming language and are managed by AWS CodeBuild.

        

        language -> (string)

          

          The programming language for the Docker images.

          

          

        images -> (list)

          

          The list of Docker images that are related by the specified programming language.

          

          (structure)

            

            Information about a Docker image that is managed by AWS CodeBuild.

            

            name -> (string)

              

              The name of the Docker image.

              

              

            description -> (string)

              

              The description of the Docker image.

              

              

            

          

        

      

    

  

