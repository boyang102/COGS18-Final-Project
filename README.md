# COGS18-Final-Project
Here is my final project
#!pip install --user nltk
import string
import random
import nltk
import matplotlib.pyplot as plt
import numpy as np
import matplotlib.pyplot as plt
#create a pie chart to represent the percent of each part in our final grades

labels = ['assignment','coding lab','final project','exam'] #labels
sizes = [35,10,15,40]  
explode = (0,0.1,0,0)  

plt.pie(sizes,explode=explode,labels=labels,autopct='%1.1f%%',shadow=False,startangle=90)
plt.axis('equal')   
plt.show()
#finish the grade calculator for cogs18 first

def cogs18_calculator():
    
    '''
    
    Do a Chatbot to let the student who want to use the calculator to get their percent of final grades
    
    '''
    
    #remember all the grades we entered best equal to float.
    #assignment grade
    
    assignment=float(input("Enter your percent of assignment grade here:     "))

    while assignment>100 or assignment<0:
        print ("Enter Error. Try Again!")
        assignment=int(input("Enter your percent of assignment grade here:     "))
    
    
    assignment_grade=str(assignment *0.35)
    print ("The part of your Assignment grade in total percent is"+" "+assignment_grade +" percent in total")


    #coding lab grade
    
    coding_lab=float(input("Enter your percent of coding lab grade here:     "))

    while coding_lab>100 or coding_lab<0:
        print ("Enter Error. Try Again!")
        coding_lab=int(input("Enter your percent of coding lab grade here:     "))
    
    
    cl_grade=str(coding_lab *0.1)
    print ("The part of your coding lab grade in total percent is"+" "+cl_grade +" percent in total")


    #final project grade
    
    final_project=float(input("Enter your percent of final project grade here:     "))

    while final_project>100 or final_project<0:
        print ("Enter Error. Try Again!")
        final_project=int(input("Enter your percent of coding final_project here:     "))
    
    
    fp_grade=str(final_project *0.15)
    print ("The part of your final_project grade in total percent is"+" "+fp_grade +" percent in total")


    #exam grade
    
    exam=float(input("Enter your percent of exam grade here:     "))

    while exam>100 or exam<0:
        print ("Enter Error. Try Again!")
        exam=int(input("Enter your percent of exam grade here:     "))
    
    
    exam_grade=str(exam *0.4)
    print ("The part of your exam grade in total percent is"+" "+exam_grade +" percent in total")


    #extra credit
    
    extra_credit=float(input("Enter your percent of extra credit here:     "))

    while extra_credit<0:
        print ("Enter Error. Try Again!")
        extra_credit=int(input("Enter your percent of coding lab grade here:     "))
    
    
    extra_grade=str(extra_credit)
    print ("The part of your extra credit in total percent is"+" "+extra_grade+" percent in total")

    #calculate for the total percent
    
    total=float(assignment_grade)+float(cl_grade)+float(fp_grade)+float(exam_grade)+float(extra_grade)
    print ("Your total grade earned in COGS 18 is "+str(total)+" percent.")
    #test cell below to test the cogs18_calculator

def test_cogs18_calculator():
    
    
    #First test it by using callable and isinstance.
    
    assert callable(cogs18_calculator)
    
    assert assignment
    assert isinstance(assignment, float)
    
    assert coding_lab
    assert isinstance(coding_lab, float)
    
    assert final_project
    assert isinstance(final_project, float)
    
    assert exam
    assert isinstance(exam, float)
    
    assert extra_grade
    assert isinstance(extra_grade, float)
    
    
    #The below contains all the extreme instances.
    
    assert assignment==101
    assert assignment=="Enter Error. Try Again!"
    assert assignment==-1
    assert assignment=="Enter Error. Try Again!"
    
    assert coding_lab==101
    assert coding_lab=="Enter Error. Try Again!"
    assert coding_lab==-1
    assert coding_lab=="Enter Error. Try Again!"
    
    assert final_project==101
    assert final_project=="Enter Error. Try Again!"
    assert final_project==-1
    assert final_project=="Enter Error. Try Again!"
    
    assert exam==101
    assert exam=="Enter Error. Try Again!"
    assert exam==-1
    assert exam=="Enter Error. Try Again!"
    
    assert extra_credit==-1
    assert assignment=="Enter Error. Try Again!"
    
    
    #Then, it is the time for us to test other normal things.
    
    assert assignment==100
    assert assignment_grade=='35'
    
    assert coding_lab==100
    assert cl_grade=='10'
    
    assert final_project==100
    assert fp_grade=='15'
    
    assert exam==100
    assert exam_grade=='40'
    
    assert extra_credit==2
    assert extra_grade=='2'
    #Now, it's time for us to define how to calculate the grade level. Let's call the function total grades.

def total_grades(total):
    
    '''
    
    Now, let us convert the percent into our grading by use the total we get.
    
    '''
    
    #enter our grading method:
    
    if total>=97:
        return('You will receive A+ in this class!')
        
    elif total>=94:
        return('You will receive A in this class!')
        
    elif total>=90:
        return('You will receive A- in this class!')
        
    elif total>=87:
        return('You will receive B+ in this class!')
        
    elif total>=84:
        return('You will receive B in this class!')
        
    elif total>=80:
        return('You will receive B- in this class!')
        
    elif total>=77:
        return('You will receive C+ in this class!')
        
    elif total>=74:
        return('You will receive C in this class!')
        
    elif total>=70:
        return('You will receive C- in this class!')
        
    else:
        return('You will fail this class!')
        
    # the function will print your final grade in the end!
    #a smoke test here. When you receive 90 percent of the total point, you will receive the A-

total_grades(90)
#Also,let's write a test cell for the function above

#It is important for us to know the level of grading

def test_total_grades():
    
    '''
    
    This function helps us to select random number to test the total grades function
    
    '''
    
    assert isinstance(total_grades(100),str)
    
    assert callable(total_grades)
    
    assert total_grades(100)== 'You will receive A+ in this class!'
    
    assert total_grades(96)== 'You will receive A in this class!'
    
    assert total_grades(90)== 'You will receive A- in this class!'
    
    assert total_grades(89)== 'You will receive B+ in this class!'
    
    assert total_grades(85)== 'You will receive B in this class!'
    
    assert total_grades(82)== 'You will receive B- in this class!'
    
    assert total_grades(78)== 'You will receive C+ in this class!'
    
    assert total_grades(75)== 'You will receive C in this class!'
    
    assert total_grades(70)== 'You will receive C- in this class!'
    
    assert total_grades(69.3)=='You will fail this class!'
    
test_total_grades()
#run the cell to test the above function which we've already defined.
def feeling():
    
    '''
    
    This function helps us to test the feelings of students towards COGS18 class.
    
    '''
    
    feeling=input("Enter your feeling to this course. Is it good, bad, or still no opinion? : ")
    
    if feeling=='good':
        print('Nice to hear that!')
        
    elif feeling=='bad':
        print('Sorry to hear that!')
        
    else:
        print('Ummm')
        
    # The above function helps us to get the feedback from students especially on the part of feeling
    # A test cell for the above function feeling()

def test_feeling():
    
    '''
    
    What happens if students enter the feeling of good, bad, or others?
    
    '''
    
    #If students give positive feedback
    
    assert feeling=='good'
    assert feeling=='Nice to hear that!'
    
    
    #If students give negative feedback
    
    assert feeling=='bad'
    assert feeling=='Sorry to hear that!'
    
    
    #If students enter other thing...
    
    assert feeling=='☺'
    assert feeling=='Ummm'
    def satisfication():
    
    '''
    
    This function helps us to test the satisfication of students towards the COGS18 class
    
    '''
    
    satis=input('Do you feel satisfied to this course teaching by professor Ellis? Yes or No?:')
    
    if satis=='Yes':
        print('Thank you for your satisfication!')
        
    if satis=='No':
        improvement=input('Can you offer a way to improve that?')
        print('Thank you for pointing out! We will improve our course soon!')
    
    #students can choose to answer 'Yes' or 'No' from the question to post their level of satisfication
    # A test cell for the above function satisfication()

def test_satisfication():
    
    '''
    
    To test students' feedback on the level of satisfication
    
    '''
    
    #If students answer 'Yes'
    
    assert satis=='Yes'
    assert satis=='Thank you for your satisfication!'
    
    #If students answer 'No'
    
    assert satis=='No'
    assert satis=='Thank you for pointing out! We will improve our course soon!'
    def teaching_team():
    
    '''
    
    This function helps us to test the satisfication of teaching team from students towards the COGS18 class
    
    '''
    
    team=input('How do you feel the teaching team? Do you love your TA or professor? Yes or No?:')
    
    if team=='Yes':
    
        print('Glad to hear that!')
    
    if team=='No':
        
        print('Oh...')
    
    #students can choose to answer 'Yes' or 'No' from the question to post their level of satisfication of teaching team.
    # A test cell for the above function teaching_team()

def test_teaching_team():
    
    '''
    
    To test students' feedback on the level of satisfication of teaching team
    
    '''
    
    #If students answer 'Yes'
    
    assert team=='Yes'
    assert team=='Glad to hear that!'
    
    #If students answer 'No'
    
    assert team=='No'
    assert team=='Oh...'
    def pay_off():
    
    '''
    
    This function helps us to test the hard-working of students towards the COGS18 class
    
    '''
    
    pay=input('Do you Think your hard work pays off? Yes or No?:')
    
    if pay=='Yes':
        
        print('Great!')
        
    if pay=='No':
        
        print('That sounds bad o(╥﹏╥)o')
    
    #students can choose to answer 'Yes' or 'No' from the question to post their rhought to level-of payoff.
    # A test cell for the above function pay_off()

def test_pay_off():
    
    '''
    
    To test students' feedback on the level of hard-working
   
    '''
    
    #If students answer 'Yes'
    
    assert pay=='Yes'
    assert pay=='Great!'
    
    #If students answer 'No'
    
    assert pay=='No'
    assert pay=='That sounds bad o(╥﹏╥)o'
    #run this code to process our survey!☺

def do_a_survey():
    
    '''
    Combine all of the functions we have from the beginning
    
    '''
    feeling()
    satisfication()
    teaching_team()
    pay_off()
    
    print("Thank you for your participatuon! You've been finished the survey.Have a good day!☺")
    #run this cell to do the survey
#do_a_survey()
def cogs18_final_project():
    cogs18_calculator()
    total_grades(total)
    do_a_survey()
cogs18_final_project()
