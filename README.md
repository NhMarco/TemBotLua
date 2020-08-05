# TemBotLua Documentation

You need to use every method with tblua:METHOD.
Make sure the import is written in the 1 line.
Read the important methods like RegisterTemTemWindow() and GetAreaColor() before you interact with scripts that needs that the variables are set inside of the Framework.
VirtualKeyCode list: https://docs.microsoft.com/en-us/windows/win32/inputdev/virtual-key-codes

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

void PressKey(int key)

    Press Key 1 time, needs a valid VirtualKeyCode in integer to work
    
void KeyUp(int key)

    Release Key, needs a valid VirtualKeyCode in integer to work
    It will release the key, when key is not pressed nothing happens
    
void KeyDown(int key)

    Hold Key, needs a valid VirtualKeyCode in integer to work
    It will press the key down till KeyDown() is called with the same key
    
void RandomArea()
    
    Starts the Random movement, it only proceeds till a movement change is done, need to be called in a while to be a real movement

void StopMovement()
    
    Stop the Area Detection threads, you can restart them with calling a movement

Boolean GetMovementState()
    
    returns true when Area Detection threads are running | false when not

void DelayTopDown()
    
    Starts the DelayTopDown movement, need to be called in a while to be a real movement
    This movement doesnt start the Area Detection threads, StopMovement doesnt do anything here

void DelayLeftRight()
    
    Starts the DelayLeftRight movement, need to be called in a while to be a real movement
    This movement doesnt start the Area Detection threads, StopMovement doesnt do anything here

void AreaLeftRight()
    
    Starts the AreaLeftRight movement, need to be called in a while to be a real movement

void AreaTopDown()
    
    Starts the AreaTopDown movement, need to be called in a while to be a real movement

void CircleArea()
    
    Starts the CircleArea movement, need to be called in a while to be a real movement

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
    
void CheckPause()

    checks pause and pausetime from TemBot, when timer is reached it will pause
    
void CheckLogout()

    checks logout from TemBot, when timer is reached it will logout
