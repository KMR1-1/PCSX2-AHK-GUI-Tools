# PCSX2-AHK-GUI-Tools
Create an interface to easly TAS PS2 Games

## GUI
+ Display slot name
+ display actual frame

### Button :
  + launch sequence from savestate
  + new sequence
    * slot nuber
    * actual frame
    * phase name
  + select slot
  + making a slot tree for parallel universe saves
  + load backup slot
  + create new slot
  + link ahk to PID
  + enter character pos address [y,z,x]

### TO DO :
+ Matrice : input, frames
  * this will create an ahk file that execute a list of Controller input
  * when the launch sequence button is pressed:
    - load the sslot related to the sequence
    - wait until save succesfully loaded
    - launches the sequence
    - maybe add functions to display the character's position over time
    - aslo display related geometry

+ Joystick Angle Cursor
  * List of all possible angles (joystick is not just a circle, it(s a disc with lengthx*lengthy possibilities
  - need to find the fullspeed raduis of joystick for platforming games
  - because xjoy and yjoy input has a min and max value, the number of angles are limited
  - ignore the values inferior to the fullspeed radiud of the joystick, they are irrelevant.
    - sqrt(sinjx²+cosjx²) >= fullspeedRadius
  - also values like 100,100 and 99,99 are the same angles so if angle1 = angle2, well take the highest value
  - also need to know the natual values that the console / game can be entered
    - for intance Vjoy LStick.X is 0.00 to 100.00, and gamecube is 0->255
  - knowing how to read the game angles (character, camera) are they floats, int ?
    


## ideas :
  + when you need to turn from an angle made out of two wall, locate the position of the angle :
    - get the line function of a wall (if the walls are slopes, prey, youll find a way)
      * run into the first wall at 2 different location and save the two character"s position
      * run into the other wall at two different location and save the second character's position
      * get the cross line differential equation to get the intersection coordinate
    - interpret the hitbox size
      * depending on the hitbox size of the character, the point is not in exact position
      * you character position bonking the wall is perpendicualrly distant by your hitbox radius
      * so we need to enter a variable that is the estimated hitbox size (supposing the hitbox is a cylinder)
      * run straitline into the approximative angle coordinate of the two walls, and see if you bump a wall
      * if you bonk the wall it means your hitbox is bigger than estiamted, increase the hitbox size
      * if not reduce the hitbox size variable of your hitbox until you barely touch the wall
      
  + Find the excat joy angle (LeftStickX, LeftStickY)
     - you need just 3 "X,Y" coordinates :
       * 'character's actual position', 'you'
       * 'character's posotion after mooving in a direction 1 frame', 'you 2'
       * 'The posotion you are aiming', 'goto'
     - you can calculate the 'angle1' between 'you' and 'goto'
     - you can also calculate the 'angle2' between 'you' and 'you 2'
     - the difference between 'angle1' and 'angle2' will be your 'accuracy' aiming 'goto'
     
     - with that info, you can know that your stick angle is greater or messer
     - if you know that game where you say hot or cold, plus or minus, you can find the maximum acuracy
     - entering value is the tas gird
     - know if you can smally rotate camera to get an even accurate values
       * the perspective squishes the angles
       * so if the camera is at a certain hight, it can perfectly fit to a joystick angle input
       * the camera can also be turned very slightly and not at max speed
       * for instance leftStickX has a sensibility so you'll have a minimum possible value turning left for example
       * the only way turning left os to rotate the camera
       * this can be useful for long distance
    
     
      
  
