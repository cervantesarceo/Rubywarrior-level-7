Rubywarrior-level-7
===================

level-7

class Player

   def play_turn(warrior)
     if warrior.feel.wall?
        warrior.pivot!
       elsif warrior.feel.empty? and @enemyless == nil
            warrior.walk!
             
         
           elsif warrior.feel.enemy?
                  warrior.attack!
                 @enemyless = 1
                 
      

                  elsif warrior.feel.empty? and @enemyless == 1 and @seguro == nil
                    warrior.walk!(:backward)
                    @seguro = 1
                   elsif warrior.feel(:backward).wall? and @seguro == 1 and warrior.health <19 and @enemyless == 1
                          warrior.rest!
                        
                         elsif warrior.feel.empty? and @enemyless == 1
                               warrior.walk!
       end
     end
   end
