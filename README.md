# PCSX2-AHK-GUI-Tools
Create an interface to easly TAS PS2 Games

Display slot name
display actual frame


TO DO :
Matrice : input, frames
Joystick Angle Cursor
List of all possible angles (joystick is not just a circle, it(s a disc with lengthx*lengthy possibilities
  need to find the fullspeed raduis of joystick for platforming games
    because xjoy and yjoy input has a min and max value, the number of angles are limited
    ignore the values inferior to the fullspeed radiud of the joystick, they are irrelevant so sqrt(sinjx²+cosjx²) >= fullspeedRadius
    also values like 100,100 and 99,99 are the same angles so if angle1 = angle2, well take the highest value
    
button
  launch sequence from savestate
  select slot
  save to slot
    slot number
    actual frame
    sequence name
  load backup slot
  backup slot
  create new slot
  link to PID
  character pos address [y,z,x]

ideas :
  when you need to turn from an angle made of two wall :
    get the line function of a wall
      run into the first wall at 2 different location and save  character"s position
      run into the other wall at two different location and save the second character's position
      get the cross line differential equation to get the intersection coordinate
    interpret the hitbox size
      depending on the hitbox size of the character, the point is not in exact position, take a 10° angle from a platform level, the point is very far
      so we need to enter a variable that is the estimated hitbox size (supposing the hitbox is a cylinder
      run into the approximative angle calculated, and see if you bump the wall if yes increase the hitbox size, if not reduce the hitbox size variable until you barely touch the wall

   Find the excat joy angle
     you need just 3 informations : 'character's actual position' ; 'character's posotion after mooving in a direction 1 frame' ; 'The posotion you are aiming'
     you can calculate the angle between 'you' and the 'position you are aiming, and the 'angle between 1st you' and '2nd you'
     the difference between 'the firt angle' and 'second angle' is your 'accuracy' aiming the 'right angle'
    tell program to suggest an angle based on previous informations and display the accuracy
      doing a game of plus minus : reduce angle if difference is negative, increase angle id angle positif
    
     
      
  
