# TemBotLua Documentation

You need to use every method with tblua:METHOD.
Make sure the import is written in the 1 line.
Read the important methods like RegisterTemTemWindow() and GetAreaColor() before you interact with scripts that needs that the variables are set inside of the Framework.

Boolean IsInFight()
    returns true when in fight main window where you can choose your move | False when not

Boolean IsInWorld()
    returns true when minimap is visible | False when not

int GetEnemyCount()
    returns Enemys in fight, 0-2

String GetPixelColor(int x, int y)
    returns ColorCode (0xFFFFFF) from the choosen RELATIVE coords from temtem

String GetAreaColor()
    returns ColorCode (0xFFFFFF) from the color where the bot tries to walk for area detection
    Need to be called first before calling Movement methods!
    
void Catch()
    IsInFight() needs to be true, otherwise it will stuck, starts attacking with both tems

void Attack()
    IsInFight() needs to be true, otherwise it will stuck, starts attacking with both tems

void CatchSwitch()
    IsInFight() needs to be true, otherwise it will stuck, starts catching left and right tem

void AttackSwitch()
    IsInFight() needs to be true, otherwise it will stuck, starts attacking left and right tem

Boolean CheckLuma()
    returns true when luma is found | false when not

void PressKey(VirtualKeyCode key)
    Needs a valid VirtualKeyCode to work, for normal keys use the VK_ before like VK_F, for other keys like arrows just use as an example ESCAPE, LEFT, UP
    It will press the key 1 time
    
void KeyUp(VirtualKeyCode key)
    Needs a valid VirtualKeyCode to work, for normal keys use the VK_ before like VK_F, for other keys like arrows just use as an example ESCAPE, LEFT, UP
    It will release the key, when key is not pressed nothing happens

void KeyDown(VirtualKeyCode key)
    Needs a valid VirtualKeyCode to work, for normal keys use the VK_ before like VK_F, for other keys like arrows just use as an example ESCAPE, LEFT, UP
    It will press the key down till KeyDown() is called with the same key
    
void RandomArea()
    Starts the Random movement, need to be called after fights ends again, this loop will repeat till minimap is not visible anymore

void PauseMovement()
    Pauses the Area Detection threads, this doesnt stop Movements that are running

void ResumeMovement()
    Resume the Area Detection threads

Boolean GetMovementState()
    returns true when Area Detection threads are running | false when not

void DelayTopDown()
    Starts the DelayTopDown movement, need to be called after fights ends again, this loop will repeat till minimap is not visible anymore
    This movement doesnt start the Area Detection threads, Pause/Resume movement doesnt do anything here

void DelayLeftRight()
    Starts the DelayLeftRightmovement, need to be called after fights ends again, this loop will repeat till minimap is not visible anymore
    This movement doesnt start the Area Detection threads, Pause/Resume movement doesnt do anything here

void AreaLeftRight()
    Starts the AreaLeftRight movement, need to be called after fights ends again, this loop will repeat till minimap is not visible anymore

void AreaTopDown()
    Starts the AreaTopDown movement, need to be called after fights ends again, this loop will repeat till minimap is not visible anymore

void CircleArea()
    Starts the CircleArea movement, need to be called after fights ends again, this loop will repeat till minimap is not visible anymore

Boolean IsKeyPressed(VirtualKeyCode key)
    returns true when key is pressed | false when not

void TestMessage(String message)
    A message from TemBotFramework appears
    
void RegisterTemTemWindow()
    Need to be called first over everything else when TemTem is the main window to register the Window positions!
    
Boolean WaitLoop(Boolean keeptem)
      returns true when world is found | false when not / when in fight
      needs boolean argument true for keep all tems or false for not
      you can use that in fights after you attacked/catched, this handles everything in fight, release/keep tems, pressing exp away

void Sleep(int sleep)
      sleep in milliseconds

void SendTelegramMessage(String message)
      sends a telegram message to the notification id in tembot
