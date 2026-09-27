# high-FoV-samples
compiling a small directory of nifty high-FoV demos and explanations.
my take on panini/stereographic at bottom.

here i put sources and engines that make use of any projections excluding rectilinear, as rectilinear is the standard in all games. you wouldn't want rectilinear projection for above 130fov anyways, not when panini exists.

https://thunderstore.io/c/white-knuckle/p/BusinessInc/Wide_Angle_Camera/ Mod for white knuckle, uses cubemaps. some projections avaliable with degree up to 360 avaliable depending on projection used.

https://www.youtube.com/watch?v=ImXwLXYBImA - explains performance issues when trying to use vastly higher FoV and cubemapping

Unreal Engine 4 or 5 for the panini and stereographic upscaling post-processors. has pixel-distortion problems however.


My take:

i think cubemaps are the way to go about this, maybe something between dynamically scaled per-face resolutions and culling the faces themselves? unsure what would go well, but somewhere around those two.
alternatively, if the industry of games was to go for a rectilinear remap to panini or otherwise, then a foveated rendering like what meta (formerly oculus) does. as to solve the major distortion at center-screen and reduce pixels at outer edges to help balance performance somewhat.

the youtube video explaining performance issues is the best source here in regards to cubemaps, because it also has a tringular prism cubemap in the explanation. they also too mention a dynamic rendering for the cubemaps too.

i wonder if a viewport could be taken and directly halved without ever adjusting the 'centerpoint' at all. maybe pixels could be recovered that way?
