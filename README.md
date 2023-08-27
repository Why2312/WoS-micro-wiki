# WoS-micro-wiki
Wiki for waste of space microcontrollers [UNSTABLE]

Methods
Valid CanvasContexts are "2D" | "3D".
ARPartObject:GetCursors() - Returns a list of AR cursors
ARPartObject:GetCursor() - Returns the part owner's cursor, or any other player's cursor if the owner does not have a cursor (this is considered the primary user)
ARPartObject:GetDimensions() - Grabs the screen dimensions of the primary user, or returns a 0, 0 Vector2
Screen:GetCanvas(context: CanvasContext?) - Retrieves the screen's canvas instance (depending on the context you may retrieve either the 3D or 2D canvas for AR parts)
Screen:ClearElements(context: CanvasContext?) - Clears the screen completely for the given context
Screen:CreateElement(elementName: string, properties: {[string]: any}, context: CanvasContext?) - Creates a new element, placing it into the screen's canvas. You can use Part, Ball, Block, Wedge, etc in the 3D canvas, the 2D canvas is the same way that other screens work
ARPartObject:ClearElements3D() - Clears 3D elements (shorthand for Screen:ClearElements("3D")
ARPartObject:CreateElement3D(elementName: string, properties: {[string]: any}) - Shorthand for CreateElement with 3D context.

Additionally, ARGlasses have all the same methods & events as Microcontroller.

Events
UserInput - Same as Keyboard's UserInput event
KeyPressed - Same as Keyboard's KeyPressed event
CursorMoved - Fired when the cursor updates at all (it's a bit weirdly named)
CursorPressed - Fires when you click down
CursorReleased - Fires when you click up

Cursors
Cursors have the following data:
Target - The PartObject that is being hovered over. You can call methods on this part!
Player - The name of the player the cursor is for
UserId - The user ID of the player
Pressed - A boolean for whether or not the mouse button is pressed
X and Y - The X and Y position on the screen
VirtualTarget - The hovered part in the virtual 3D space
Hit - Synonymous to Roblox's PlayerMouse.Hit
Origin - Synonymous to Roblox's PlayerMouse.Origin
UnitRay - Synonymous to Roblox's PlayerMouse.UnitRay
WorldPosition - The world position of the mouse cursor
VirtualWorldPosition - The world position of the mouse cursor in the virtual 3D space
ScreenPosition - The XY screen position of the mouse cursor
UserInput - A table of input data (would suggest printing with repr) - Contains Mouse, Keyboard, Gamepad, VREnabled, KeyboardEnabled, TouchEnabled, GamepadEnabled, and LastInputType
MouseDelta - The current delta of the mouse for the frame that was sent
UserCFrames - Contains Head, LeftHand, and RightHand for VR, equivalent to UserInputService's GetUserCFrame
Camera - An object containing:
ViewportSize - The size of the camera viewport
ViewportSizeUI - The size of the camera viewport (2D UI context)
CFrame
Focus
RenderCFrame - The CFrame the camera is rendered at (for VR)
NearPlaneZ
HeadScale
CameraType
FieldOfView
DiagonalFieldOfView
MaxAxisFieldOfView
FieldOfViewMode
