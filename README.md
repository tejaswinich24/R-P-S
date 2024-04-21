import random

print("\t\t#ROCK-PAPER-SCISSORS GAME#")
print("Instructions: Rock beats scissors, scissors beat paper, and paper beats rock.")
print("Each round consists of 5 chances.")

choices=("rock","paper","scissors")
print("Enter: rock / paper / scissors")

def rps():
    
    player_score=0      #count for each win of computer
    computer_score=0   #count for each win of player
    
    c_cnt=0     #count for each score of computer
    p_cnt=0     #count for each score of player
    
    i=0
    for i in range(5):
        pl=input("\nPlayer : ")
    
        comp=random.choice(choices)
        print("Computer : ", comp)
    
        if((comp=="rock" and pl=="scissors") or (comp=="scissors" and pl=="paper") or (comp=="paper" and pl=="rock")):
            print("--Computer scored!--")
            c_cnt+=1
       
        elif((pl=="rock" and comp=="scissors") or (pl=="scissors" and comp=="paper") or (pl=="paper" and comp=="rock")):
            print("--PLayer scored!--")
            p_cnt+=1
       
        else:
            print("TIE")
    
    if(p_cnt > c_cnt ):
        print("\n** PLayer Wins! **")
        player_score +=1
    
    elif(c_cnt > p_cnt):
        print("\n** Computer Wins! **")
        computer_score +=1
    
    else:
        print("Round Tie")
    
    print("\n\tScore of player: ", player_score)
    print("\tScore of computer: ", computer_score)
    
    ans=input("Do you want to play another round? (Enter y/n): ")
    if(ans=="y"):
        rps()
    else:
        print("Thanks for playing!")
        return
rps()
