# Hands Creation Tutorial
A tutorial showing how to use the <a href="https://github.com/jbusfield/uevrlib">uevrlib library</a> to add hands into UEVR games

Get the hands_tutorial_uevr_2_1_1.zip file from releases. Open the zip and drag the scripts folder into the profile directory for your game. Start with a clean profile to avoid any conflicts.

Run hand_configuration.lua. There will be a Hands Config tab in the UEVR UI. Follow the steps of the wizards to create hands for your game
<br><br><img width="357" height="351" alt="hands_config1" src="https://github.com/user-attachments/assets/186d97e1-c1d4-4ce5-a6f8-e3e3548d115c" />

After you have finished creating the hands you can comment out the
hands.enableConfigurationTool()
line in hand_configuration.lua and your hands will load automatically. Refer to the documentation in hands.lua for additional functions that can be used

## Example game
Included in the releases is hands_example_Hello_Neighbor_2_Demo.zip. This is a profile that will run in the steam game Hello Neighbor 2 Demo which is a free demo game. A simple script and a script that supports multiple attachment grips is included in the profile. Just rename one or the other from .luax to .lua to test (dont run both at once as .lua)

## Tips for Hand Animation
When creating hand animations you can create a different animation for each type of weapon (not all weapons have the same grip). Open the Attachments tree and give your animation a name then press Add Attachment.
<br><br><img width="373" height="342" alt="hands_config4" src="https://github.com/user-attachments/assets/f48b50b1-445a-4caf-acb3-c38140343034" />

Now when you select Attachment Grip or Attachment Trigger as the grip type, a combo will appear allowing you to select from the attachments you created in the previous step. Create different animations for each Attachment type
<br><br><img width="379" height="345" alt="hands_config2" src="https://github.com/user-attachments/assets/e1fafc45-b6f5-4d1e-abb9-cd40934c8127" />

Also, while tweaking every finger joint for every possible weapon animation is fun, there's a much quicker way. Just make sure the original player mesh you are using is actually gripping the weapon in question, then press "Get Hand From Current Mesh". That will copy the current hand pose from the original mesh onto the hand copy for whatever Hand, Type and State you currently have selected 
<br><br><img width="379" height="346" alt="hands_config3" src="https://github.com/user-attachments/assets/f5c9d5f9-b6a5-4c9f-9d4c-50c73ed80ba1" />

Often while editing animations you may want to make the bones of one hand do the same thing as the bones of the other. You can do this by selecting "Both" for the hand rather than "Right" or "Left". But sometimes you will find that if you adjust, say the Pitch of a bone in the right hand to move toward the palm, the bone in the left hand will twist the opposite way. To address that situation there are the Mirror checkboxes next to Pitch Yaw and Roll. Each game is different so you will have to experiment with the combination of checkboxes that will work correctly for your game.
<br><br><img width="757" height="690" alt="hands_config5" src="https://github.com/user-attachments/assets/baecc1b5-51e2-47b1-8444-657e953809d8" />

<br><br>Some things to remember that could be gotchas:
1) When running hands.enableConfigurationTool() and going through the wizard its better to not run any other code because any hand code you write might conflict with the config screen
2) If your goal is be able to switch handedness, the best way is to get the right hand fully working correctly and then just copy and paste right hand to left hand for every Grip Type and Grip State.
3) Make sure you create an Attachment Grip and Attachment Trigger config for both the On and Off states. If you only create it for the On state then the hand will open when you're not actively gripping or possibly flap on/off. In most cases your Off and On states for Attachment Grip will be exactly the same so you can just do copy hand for the On state and paste it into the Off state. However if you want to make slight joint adjustments between On and Off to make it look like you're flexing your hand when gripping that's fine too. Your On and Off states for Attachment Trigger will be slightly different because On state is the trigger being pulled so your index finger joints change a bit 
