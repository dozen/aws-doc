[ :ref:`aws <cli:aws>` . :ref:`appstream <cli:aws appstream>` ]

.. _cli:aws appstream describe-images:


***************
describe-images
***************



===========
Description
===========



Describes the images. If a list of names is not provided, all images in your account are returned. This operation does not return a paginated result.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/appstream-2016-12-01/DescribeImages>`_


========
Synopsis
========

::

    describe-images
  [--names <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--names`` (list)


  A specific list of images to describe.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Images -> (list)

  

  The list of images.

  

  (structure)

    

    New streaming instances are booted from images. The image stores the application catalog and is connected to fleets.

    

    Name -> (string)

      

      The unique identifier for the image.

      

      

    Arn -> (string)

      

      The ARN for the image.

      

      

    BaseImageArn -> (string)

      

      The source image ARN from which this image was created.

      

      

    DisplayName -> (string)

      

      The display name for the image.

      

      

    State -> (string)

      

      The image starts in the **PENDING** state. If image creation succeeds, it moves to **AVAILABLE** . If image creation fails, it moves to **FAILED** .

      

      

    Visibility -> (string)

      

      The visibility of an image to the user; images can be public or private.

      

      

    ImageBuilderSupported -> (boolean)

      

      Whether an image builder can be launched from this image.

      

      

    Platform -> (string)

      

      The operating system platform of the image.

      

      

    Description -> (string)

      

      A meaningful description for the image.

      

      

    StateChangeReason -> (structure)

      

      The reason why the last state change occurred.

      

      Code -> (string)

        

        The state change reason code of the image.

        

        

      Message -> (string)

        

        The state change reason message to the end user.

        

        

      

    Applications -> (list)

      

      The applications associated with an image.

      

      (structure)

        

        An entry for a single application in the application catalog.

        

        Name -> (string)

          

          The unique identifier for the application.

          

          

        DisplayName -> (string)

          

          The name of the application shown to the end users.

          

          

        IconURL -> (string)

          

          The URL for the application icon. This URL may be time-limited.

          

          

        LaunchPath -> (string)

          

          The path to the application executable in the instance.

          

          

        LaunchParameters -> (string)

          

          A list of arguments that are passed to the application at launch.

          

          

        Enabled -> (boolean)

          

          If there is a problem, an application can be disabled after image creation.

          

          

        Metadata -> (map)

          

          Additional attributes that describe the application.

          

          key -> (string)

            

            

          value -> (string)

            

            

          

        

      

    CreatedTime -> (timestamp)

      

      The time stamp when the image was created.

      

      

    PublicBaseImageReleasedDate -> (timestamp)

      

      The AWS release date of the public base image. For private images, this date is the release date of the base image from which the image was created.

      

      

    

  

