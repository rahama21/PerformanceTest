# PerformanceTest

                     
# Introduction
This document explains how to run a performance test with JMeter .                              

# performance test report

I’ve completed performance test on frequently used API for test App.

50 Concurrent Request with 10 Loop Count; Avg TPS for Total Samples is 309.56 And Total Concurrent API requested: 300.

500 Concurrent Request with 10 Loop Count; Avg TPS for Total Samples is 1449.09 And Total Concurrent API requested: 3000.

While executed 500 concurrent request found 6 request Non HTTP response code and error rate is 0.20%.


# Summary

Server can handle almost concurrent 2700 API call with almost zero (0) error rate.


# Installation :   
 Java:         https://www.oracle.com/java/technologies/downloads/
      
 JMeter:      https://jmeter.apache.org/download_jmeter.cgi                     

Blazmeter:    https://chrome.google.com/webstore/detail/blazemeter-the-continuous/mbopgmdnpcbohhpnfglgohlbhfongabi?hl=en

        

# Prerequisites
1.  JMeter 5.5,Java 19 are supported.
2.  16 GB ram is good.



# Elements of a basic test plan
                
                
  1.Thread Group: The root element of every test plan.Simulates  the  (concurrent)  users and then run all requests.Each thread simulatesa single user.                   
                       
 2.HTTP Header Manager Request : Configuration Element                     
 
 
 3.HTTP Request :Sampler
                
 4.Summary Report: Listener


# Testplan:
        Testplan > Add > Threads (Users) >  Thread Group (this might vary dependent on
        the jMeter version you are using)
       

Name: Practice1

Number of Threads (users): 50 to 500

Ramp-Up Period (in seconds): 10

Loop Count: 1

    
    1.   The general setting for the tests execution, such as whether Thread Groups will run   simultaneously or sequentially, is specified
          in the item  called Test Plan.
         

    2.  All HTTP Requests will use some default  settings from the HTTP Request,such as the Server IP, Port Number, and  Content-Encoding.
       
    3.  Each Thread Group specifies how the HTTP Requests should be carried out.To determine how many concurrent "users" will be simulated, 
         one must first know the     number of threads. The number of actions  each "user" will perform is determined  by the loop count.
        
    4. The HTTP Header Manager, which allows you  to provide the Request Headers that will be utilized by the upcoming HTTP Requests, 
        is the first item in Thread  Groups  
       

     
# Website link:

# https://reqres.in/


# List of APIS
1.https://reqres.in/api/register

2.https://reqres.in/api/login

3.https://reqres.in/api/users

4.https://reqres.in/api/users/2

5.https://reqres.in/api/users/23

6.https://reqres.in/api/unknown


# Load the JMeter Script

    File > Open (CTRL + O)

    Locate the "Practice1.jmx" file contained on this repo

    The Test Plan will be loaded

<img width="951" alt="Screenshot 2022-12-06 235803" src="https://user-images.githubusercontent.com/32101980/205987123-4c7eef14-6fc8-493d-9222-8ce22683d605.png">


<img width="953" alt="Screenshot 2022-12-06 221328" src="https://user-images.githubusercontent.com/32101980/205988220-f4b02dba-ba9a-47b9-bd88-c691a492481d.png">


<img width="954" alt="Screenshot 2022-12-06 221256" src="https://user-images.githubusercontent.com/32101980/205988269-77cc682c-4baf-4a87-b24b-eb0b768ba7a2.png">



# Test execution (Terminal)
    JMeter should be initialized in non-GUI mode.
    Make a report folder in the bin folder.
    Run Command in jmeter\bin folder.
    
# Make Jtl file
    n: non GUI mode
    t: test plan to execute
    l: output file with results
    
    jmeter -n -t  Practice1_50.jmx -l OPENCART_T1.jtl
# Make html file
    jmeter -g report\OPENCART_T1.jtl -o OPENCART_T1.html
  
    g: jtl results file

    o: path to output folder
    
  <img width="545" alt="Screenshot 2022-12-06 221436" src="https://user-images.githubusercontent.com/32101980/205991480-c7b1fa83-247a-4c00-8053-0873fd4c732f.png">
  
# HTML Report

Number of Threads 50 ; Ramp-Up Period 10s

## requestsummary

<img width="743" alt="Screenshot 2022-12-07 002727" src="https://user-images.githubusercontent.com/32101980/205992425-47e24cc1-a13a-4d74-b107-7438766a46bf.png">

## errors

<img width="736" alt="Screenshot 2022-12-07 002826" src="https://user-images.githubusercontent.com/32101980/205992457-03557c7e-bb49-4a99-99d2-ea6548794518.png">

Number of Threads 500 ; Ramp-Up Period 10s

## requestsummary

<img width="732" alt="Screenshot 2022-12-06 213157" src="https://user-images.githubusercontent.com/32101980/205993092-0d6e40c2-3285-48a5-bf05-a0283ac98da4.png">


## responsetime


<img width="721" alt="Screenshot 2022-12-06 213455" src="https://user-images.githubusercontent.com/32101980/205993119-0972c1a0-994c-4172-9ef3-fad0e989bdb1.png">

## errors
<img width="710" alt="Screenshot 2022-12-06 214115" src="https://user-images.githubusercontent.com/32101980/205993145-d99658c4-d6a5-49d3-a6c0-277ae30e2af9.png">



# Stress Testing
  Stress Testing is a type of software testing that evaluates how the software responds under extreme conditions. It verifies how robust a system will be, and its        response capabilities and error handling when it is subjected to conditions where its normal functioning can be compromised.
  
## requestsummary

<img width="732" alt="Screenshot 2022-12-06 213157" src="https://user-images.githubusercontent.com/32101980/205993092-0d6e40c2-3285-48a5-bf05-a0283ac98da4.png">

## errors
<img width="710" alt="Screenshot 2022-12-06 214115" src="https://user-images.githubusercontent.com/32101980/205993145-d99658c4-d6a5-49d3-a6c0-277ae30e2af9.png">


# Spike Testing
Spike testing is a type of performance testing where the demand for an application is suddenly and drastically increased or decreased. Spike testing's objective is to ascertain how a software program will behave under highly variable traffic conditions.




## requestsummary

<img width="732" alt="Screenshot 2022-12-06 213157" src="https://user-images.githubusercontent.com/32101980/205993092-0d6e40c2-3285-48a5-bf05-a0283ac98da4.png">

## errors
<img width="710" alt="Screenshot 2022-12-06 214115" src="https://user-images.githubusercontent.com/32101980/205993145-d99658c4-d6a5-49d3-a6c0-277ae30e2af9.png">



  
  




