# the code is written in purely python 3.8, no database or additional program required
import random

# empty list to accept names of friends
lista = []
invite = int(input("Enter the number of friends joining (including you): \n "))

if invite <= 0:
    print("No one is joining for the party")
elif invite > 0:
    # input prompt that accepts the list of friends, the number of prompt is determine by the value of "invite"
    print("Enter the name of every friend (including you), each on a new line: \n")
    for n in range(invite):
        a = input()
        lista.append(a)
    # "lucky" to determine if a friend can be lucky not to partake in sharing part of the bill
    lucky = input('Do you want to use the "Who is lucky?" feature? Write Yes/No: \n').lower()
    # total bill as an input and converted to float since input is always as a string
    total_bill = float(input("Enter the total bill value: \n"))
    if lucky == "yes":
        # a lucky member will be chosen by random
        lucky_mem = random.choice(lista)
        # print the name of the lucky member
        print("{} is the lucky one!".format(lucky_mem))
        # Now it is time to calculate bill to be shared by other friends excluding the lucky member
        lucky_index = lista.index(lucky_mem)
        lista.pop(lucky_index)
        # Bill divided equally among friends excluding the lucky member
        av_bill = round((total_bill / float(invite - 1)), 2)
        # friends (dic) updated excluding the lucky member
        friends = dict.fromkeys(lista, av_bill)
        # Now is time to update the friend (dic) by including the lcuky member
        d = {lucky_mem: 0}
        friends.update(d)
        # print friend (dic) including bills to be paid only the lucky member will 0 bill to pay
        print(friends)
    elif lucky == "no":
        # if No lucky member is selected, it means all friends will share bills equally
        print("No one is going to be lucky")
        av_bill = round((total_bill / float(invite)), 2)
        friends = dict.fromkeys(lista, av_bill)
        # print friends (dic) with bills shared equally
        print(friends)
    else:
        print("Invalid input")
else:
    print("invalid input") 
