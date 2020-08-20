import random
from random import randint
print('welcome to maths quiz')
print('what is your name')
print('Remember to press the "enter" key after every answer')
name=input('Type your name: ')
age=int(input('what is your age: '))
x=0

questions={}
score=0
if(age<10):
  for i in range(0,7):
    int_a=randint(1,10)
    int_b=randint(1,10)
    operators=['+' ,'-','*']
    operator_value=random.choice(operators)
    question=str(int_a)+' '+str(operator_value)+' '+str(int_b)
    answer=eval(question)
    question+=':'
    questions.update({question:str(answer)})

elif(age>10):
  print('| ~~~~~~~~~~ |')
  print('| no of digits for operation |')
  print('| ~~~~~~~~~~ |')
  print('| press "1" for single digit |')
  print('| press "2" for double digit |')
  print('| ~~~~~~~~~~ |')
  count=int(input("enter your choice: "))
  for j in range(0,7):
    if(count==1):
      int_c=randint(1,10)
      int_d=randint(1,10)
    elif(count==2):
      int_c=randint(10,20)
      int_d=randint(10,20)
    else:
      print("please try again and enter a valid number")
      x=1
      break
    operators=['+' ,'-','*']
    operator_value=random.choice(operators)
    question=str(int_c)+' '+str(operator_value)+' '+str(int_d)
    answer=eval(question)
    question+=':'
    questions.update({question:str(answer)})

if(x==0):   
  print('Hi,',name+ '!' + ' all the best') 
  for q in questions.keys():
    user_answer=input(q)
    if questions.get(q)==str(user_answer):
        score+=1 
        print('correct')
    else:
        print('incorrect')
  print('you'+' '+'got'+' '+str(score)+' '+'number'+' '+'correct')
  if(score<3):
      print('need more practice')
  else:
      print('great job!keep doing well')
