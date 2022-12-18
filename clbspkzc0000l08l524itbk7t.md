# How to Set up Web Analytics for your React Website using Google Analytics and Tag Manager.

# Introduction

Recently, I had to monitor user activity on a portfolio website I built with React. I researched and found many useful platforms online that offered web analytics services but decided to opt for Google Analytics because it perfectly served the purpose I needed and was completely free to use.

In this article, I explain the process of setting up Google Analytics on a React project. Do you want to monitor the number of daily users on your website or some other useful metrics? Let's get right into it!

# Prerequisites

*   Basic Knowledge of Javascript/React is required
    
*   A Google account
    
*   A React Application hosted online.
    

# Setting up Google Analytics

Let's get into the nitty-gritty of the work.

*   First, **ensure you have an accessible google account.** A google account gives you access to a ton of free products by Google, including the one we'll be using in this tutorial i.e Google Analytics. If you do not have one, kindly click on [this link](https://www.google.com/account/about/).
    
*   Go to [Google Analytics page](https://analytics.google.com/). You should see a page like this. Click on `Start Measuring` to get started.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671323138474/btlCofM95.png align="center")
    
*   Enter a suitable account name, fill in some other data and click on the `Next` button to get started.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671323235660/fjPnZMV37.png align="center")
    
*   You should now have access to your user dashboard, it's time to get things started. If you didn't previously create a Property, click on `Create Property` and give a suitable name e.g "My Business website". Also, choose a suitable time zone.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671323501911/sRjHtGZUh.png align="center")
    
    *   Next, Click on `Data Streams` and select `Web` since we are dealing with a React app in this tutorial.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671324078040/At24T1k9s.png align="center")
        
    *   Enter the URL of the website you want to monitor and a stream name (just add a suitable name). You can also enable `Enhanced Measurement` which is recommended.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671324164922/QwEoP7Vpj.png align="center")
        
    *   You should have a similar view as the one below. You can Proceed to `View Tag Instructions` to view your tag. Take note of your Measurement ID.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671325031474/74VUzwstA.png align="center")
        
    *   Now, let us incorporate Tag Manager which helps us to use the tag on our website without much stress. Click on [this link](https://tagmanager.google.com/) and create a new account.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671325719850/0_Euu2FR0.png align="center")
        
    *   After the successful creation of an account, you should now have access to your Google Tag Manager snippet.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671325900536/BpcaFG0L3.png align="center")
        
    *   In your React Project, Paste the code into the Public `index.html` file since it is served on every render of React. Push your code and ensure it is deployed successfully.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671326057084/BHrqwmCzf.png align="center")
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671326099871/BRMZm1V0Z.png align="center")
        
    *   Back to Tag Manager to wrap things up. We're almost there :) Click on Tags on your Tag Manager Dashboard and create a new tag. Name your tag and configure it appropriately.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671326348195/cnTzbom-z.png align="center")
        
        1.  Tag Configuration: Rename the tag and select `Google Analytics GA4 Configuration`
            
        2.  Triggering: These are events that fire or block the tag. You can add as many as you'd like, and even configure custom triggers.
            
    *   Now it's time to preview whether our tags work. Click on `Preview` , enter your website URL, and Connect. A new tab is opened automatically to preview your website.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671326876311/fyIscmHEl.png align="center")
        
    *   If the Preview was successful, you should have a pop-up beneath your screen. Click on `finish` to complete the preview.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671327051047/k3kgNObVj.png align="center")
        
    *   Finally, we publish our tag by clicking on `Submit` in the previous tab.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671327155483/64M2MzITo.png align="center")
        
    *   Input a descriptive name and a suitable message. Then click on `Publish`
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671327253377/BxHlZzvrN.png align="center")
        
    *   If successful, you should have a page to confirm your configurations.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671327323422/XpiCgmLPn.png align="center")
        
    *   Finally, to test that our analytics works. We go back to our Google Analytics Dashboard and voila! We see that we have had one user in the past 30 minutes.
        

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671327483340/NsTUs5l6j.png align="center")

# Conclusion

That was such a long process, but it was worth it. Now, we can monitor user activity on our website and improve performance based on the feedback we get.

If you encountered any problems following this article or you have suggestions, please feel free to drop a comment in the section below or Reach out to me on [Twitter](https://twitter.com/@iambenjamen). I will be glad to reply your message. Cheers and keep hacking.