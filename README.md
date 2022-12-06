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
 Java:https://www.oracle.com/java/technologies/downloads/
      
 JMeter:https://jmeter.apache.org/download_jmeter.cgi                     

Blazmeter:https://chrome.google.com/webstore/detail/blazemeter-the-continuous/mbopgmdnpcbohhpnfglgohlbhfongabi?hl=en

        

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


