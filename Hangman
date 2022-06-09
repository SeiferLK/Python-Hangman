import random
import string
the_list = 'python', 'java', 'swift', 'javascript'
wins = 0
losses = 0
print('H A N G M A N\n')
while True:
    inp = input('Type "play" to play the game, "results" to show the scoreboard, and "exit" to quit:')
    if inp == "play":
        random_word = the_list[random.randint(0, len(the_list) - 1)]
        hidden_word = list('-' * len(random_word))
        guessed = ()
        attempts = 8
        while attempts > 0:
            print(''.join(hidden_word))
            letter = input('Input a letter: ')
            letter_check = list(letter)
            if len(letter_check)-1 > 0 or letter == "":
                print("Please, input a single letter.")
                continue
            if letter not in string.ascii_lowercase:
                print("Please, enter a lowercase letter from the English alphabet.")
                continue
            if letter not in random_word:
                print("That letter doesn't appear in the word.")
                guessed = guessed + (letter,)
                attempts -= 1
                if '-' in hidden_word and attempts == 0:
                    print("You lost!")
                    losses += 1
                    break
                else:
                    continue
            if letter in guessed:
                print("You've already guessed this letter.")
                attempts -= 1
                if '-' in hidden_word and attempts == 0:
                    print("You lost!")
                    losses += 1
                    break
                else:
                    continue
            if letter in random_word and letter not in hidden_word:
                for i in range(len(random_word)):
                    if random_word[i] == letter:
                        hidden_word[i] = letter
                        guessed = guessed + (letter,)                
            if '-' in hidden_word and attempts == 0:
                print("You lost!")
                losses += 1
                break
            if '-' not in hidden_word :
                print("You guessed the word " + random_word + "!")
                print("You survived!")
                wins += 1
                break
        continue    
    elif inp == "results":
        print("You won: " + str(wins) +  " times.")
        print("You lost: " + str(losses) +  " times.")
        continue
    elif inp == "exit":
        break
    break      
