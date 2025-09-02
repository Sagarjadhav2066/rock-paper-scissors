# rock-paper-scissors
SCRUM-9 nkndka
SCRUM-5 Code

import random

def get_computer_choice():
    return random.choice(["rock", "paper", "scissors"])

def get_winner(player, computer):
    if player == computer:
        return "tie"
    elif (player == "rock" and computer == "scissors") or \
         (player == "scissors" and computer == "paper") or \
         (player == "paper" and computer == "rock"):
        return "player"
    else:
        return "computer"

def main():
    print("Welcome to Rock-Paper-Scissors! Best of 5 rounds.\n")
    
    rounds = 5
    player_score = 0
    computer_score = 0

    for round_num in range(1, rounds + 1):
        print(f"--- Round {round_num} ---")
        
        player_choice = input("Enter rock, paper, or scissors: ").lower()
        while player_choice not in ["rock", "paper", "scissors"]:
            print("Invalid choice! Please try again.")
            player_choice = input("Enter rock, paper, or scissors: ").lower()
        
        computer_choice = get_computer_choice()
        print(f"Computer chose: {computer_choice}")
        
        winner = get_winner(player_choice, computer_choice)
        if winner == "player":
            print("You win this round!\n")
            player_score += 1
        elif winner == "computer":
            print("Computer wins this round!\n")
            computer_score += 1
        else:
            print("This round is a tie!\n")
    
    print("=== Final Results ===")
    print(f"Your Score: {player_score}")
    print(f"Computer Score: {computer_score}")
    
    if player_score > computer_score:
        print("🎉 Congratulations! You won the game.")
    elif computer_score > player_score:
        print("💻 Computer wins the game. Better luck next time!")
    else:
        print("🤝 It's a tie!")

if __name__ == "__main__":
    main()
