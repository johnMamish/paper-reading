Hot takes:
personal interest: 2/10
paper quality/novelty: 7?/10

360-degree VR video is a content type that's rapidly growing in popularity, however, methods for serving and rendering this content haven't gone beyond methods used for planar, rectangular video.

This is a problem, because there's an implicit "VR tax" built in; to render video on the client side, the server sends the spherical, 360-degree video as a flattened rectangle, and then the client has to take the user's head position (which only the client knows in real-time) and do a series of expensive transformations that are unique to VR on the video.

The authors propose 2 methods for improving performance
  * use of neural networks to estimate user head movement, so that only relevant pieces of data are (sent? processed? preprocessed on the server side? not sure.)
  * design of a novel HW accelerator specific to viewing 360 degree video.