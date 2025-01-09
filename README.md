# Timer-Tutorial
Tutorial on how to make a simple timer in Unity

# Objective 
The objective of this tutorial is to learn how to create a simple timer so that you can add it to any of your unity projects.

# Getting Started 
In our new project we are going to create an empty and name it `TimerManager` once this is create go to our ptoject files and in the scripts folder create a new c# script calle `timeManager`. Open the script at we can start to code. 

# Coding 
Before we get started to cretae a timer in unity the best way to do it is using a property calkled `Time.deltaTime` this represents the time elapsed in seconds since the last frame, its commonly used to make calculation frame rates independant. what we need to do is multiply a `float` with this `Time.deltaTime` and that mwans we are going to be scaling this value based on the time that has passed since the previous frame and this allows us to create smooth answers consistent timer regardless of the frame rate. More information on [`Time.deltaTime`https://docs.unity3d.com/6000.0/Documentation/ScriptReference/Time-deltaTime.html]. 

Now in Visual studio at the top we are going to create a `public float` called `timer` and then in our update function we can write a `timer += Time.deltaTime` and as I explained before here we are just incrasing this timer by the elapsed time since the last frame and this is done every frame because its in our update function. [`Update` https://docs.unity3d.com/6000.0/Documentation/ScriptReference/MonoBehaviour.Update.html]. Your script should look like this. 


<img width="1190" alt="Screenshot 2025-01-09 at 15 31 51" src="https://github.com/user-attachments/assets/f926ed15-adad-4bf5-a249-a7c0a23e23e4" />

Bck in unity you can see that in your TimerManger you have a timer value, you can test if it works by pressing play and with your Timemanager selected you can see that the value of timer is going up. 
# UI

Now to be able to see the timer you have to create a UI but this is very simple to do. 
Right click in the hierarchy go to `UI` and create a `text` this will automaticaly create a Canvas as well as the text. Call the text `timerText` go into your canvas and make sure that the UI scale mkode is set to `Scale with screen size`. Now with our `timeText` selected press `F` and it will take you to ypur text, here you can play around with the settings of the text, change the colour, scale font and get it to your liking, make sure in the text you write `Timer` once ypou are done we can head back to our script. 

# More Coding 

In our scrip we have to reference our timer in our script to our UI, when referencing we need to use the unity space name. At the top of our code write `using UnityEngine.UI` and then we need to get a reference to our UI timer so under our timer float we can write `public Text timerText` and in our update function we say that our timerText is equal to our timer. your script should look like this so far. 

<img width="1190" alt="Screenshot 2025-01-09 at 16 14 26" src="https://github.com/user-attachments/assets/b449273e-ef8b-4a00-8a8b-24d7873c8bb1" />

Here we get an error saying that we cannot convert a tipe of a float into a [`String` https://docs.unity3d.com/560/Documentation/ScriptReference/String.html] so at the end of our timer we can add a `.ToString` to fix it. now your code should look like this since now our timer is converted to a `String`. 

<img width="1190" alt="Screenshot 2025-01-09 at 16 17 43" src="https://github.com/user-attachments/assets/b8a4b16f-20c2-44ab-9460-fdf02a1177a2" />

# Finishing

Back in unity you should be able to see the Timer Text float in your `TimeManager` script, from the hierarchy drag and drop your timer Text into the float this is how it should look like, and now when you press play you can see your timer. But as you can see its not the best looking timer so we can fix this with a tiny bit more coding. 

<img width="449" alt="Screenshot 2025-01-09 at 16 26 25" src="https://github.com/user-attachments/assets/db354e17-f390-4f27-b8a0-9a1c8dea53d6" />

Back in our code you can see that next to our `ToString` we have brackets and what we can put in here is a [`Format Specifier` https://docs.unity3d.com/Packages/com.unity.logging@1.2/manual/format-specifiers.html] this provides instruction on how the value should be formated, in our case the amount of decimal places. to do this inside the brackets use quotation marks and then `F` and then we use a number to define how many decimals we want to have this is totaly up to your preference, for example if you wanted to have 3 decimals you do `"F3"` nad if you dont want any and just want whole numbers do `"F0"`. Now save and we are done you can head bacok to unity and you will have a simple working timer. Your final script should look something like this. 

<img width="937" alt="Screenshot 2025-01-09 at 16 34 00" src="https://github.com/user-attachments/assets/ecd26b2d-6832-445b-a2f5-840fa9cb54e5" />


I got the reference for this tutorial from https://www.youtube.com/watch?v=BMsiidirbYs 
