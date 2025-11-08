# hands_tutorial_uevr
A tutorial showing how to use the uevrlib to add hands into UEVR games

Drag the scripts folder into the profile directory for your game. Start with a clean profile to avoid any conflicts.

Run hand_configuration.lua. There will be a Hands Config tab in the UEVR UI. Follow the steps of the wizards to create hands for your game
<br><br><img width="357" height="351" alt="hands_config1" src="https://github.com/user-attachments/assets/186d97e1-c1d4-4ce5-a6f8-e3e3548d115c" />

After you have finished creating the hands you can comment out the
hands.enableConfigurationTool()
line in hand_configuration.lua and your hands will load automatically. Refer to the documentation in hands.lua for additional functions that can be used
