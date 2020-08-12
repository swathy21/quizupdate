from random import randint
print('welcome to maths quiz')
print('what is your name')
print('Remember to press the "enter" key after every answer')
name=input('Type your name')
age=int(input('what is your age'))
print('Hi,',name+ '!' + 'all the best')

questions={}
score=0
if(age<10):
  for i in range(5):
    int_a=randint(1,10)
    int_b=randint(1,10)
    question=str(int_a)+' '+str('*')+' '+str(int_b)
    answer=eval(question)
    question+=':'
    questions.update({question:str(answer)})

elif(age>10 and age<20):
  for j in range(5):
    int_c=randint(1,10)
    int_d=randint(1,10)
    question=str(int_c)+' '+str('*')+' '+str(int_d)
    answer=eval(question)
    question+=':'
    questions.update({question:str(answer)})
    
for q in questions.keys():
  user_answer=input(q)
  if questions.get(q)==str(user_answer):
      score+=1 
      print('correct')
  else:
      print('incorrect')
print('you'+' '+'got'+' '+str(score)+' '+'number'+' '+'correct')
if(score<5):
    print('need more practice')
else:
    print('great job!keep doing well')
