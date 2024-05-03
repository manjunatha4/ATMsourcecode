# https-github.com-MANJUNATHAR
# project name is automatic teller machine (ATM)

'''1.check_balence
   2.deposit
   3.withdraw
   4.set_pin
   variables: bal=0
              og_pin=none'''


# create set_pin function
bal=0
og_pin= None


def set_pin():
    global og_pin
    while True:
        print('_'*100)
        if og_pin==None:
            pin_1=int(input('enter the 4 digit pin: '))
            pin_2=int(input('conform your pin: '))
            if pin_1==pin_2:
                print('pin set successful')
                og_pin=pin_1
                break
            else:
                print('incorect pin ')
        else:
            print('pin is already set')

        
            
def check_bal():
    pin=int(input('enter the 4 digit pin: '))
    if pin==og_pin:
        print('available balance in your A/C is',bal,'RS')
    else:
        print('incorrect pin ')

def deposit():
     global bal
     pin=int(input('enter the 4 digit pin: '))
     if pin==og_pin:
         amt=int(input('enter the amount to deposit: '))
         bal+=amt
         print('amount of ',amt, 'RS. deposited successfully')
     else:
         print('incorrect pin or pin is not matched')

def withdreaw():
     global bal
     pin=int(input('enter the 4 digit pin: '))
     if pin==og_pin:
         amt=int(input('enter the amount to withdraw: '))
         if amt<=bal:
            bal-=amt
            print('amount of ',amt, 'RS. withdrawed successfully')
         else:
             print('insuficiant funds ')
     else:
         print('incorrect pin or pin is not matched')

def services():
    while True:
        print('^'*90)
        print('-----WELCOME TO ATM------')
        print('enter 1.deposit 2.withdraw 3.check balance 4.set PIN 5.Exit ')
        ch=int(input('enter the choice: '))
        if ch==1:
            deposit()
        elif ch==2:
            withdreaw()
        elif ch==3:
            check_bal()
        elif ch==4:
            set_pin()
        elif ch==5: 
            print('-----thank you for using our services-----')
            break
        
        a=input('do you want to continue y/n: ')
        if a.lower()=='y':
           continue
        
        else:
            print('thank you for using our ATM services....')
            break
        
        
services()    









    


