# How to ask every college in America for a T-Shirt

This repository holds the code used to make this [TikTok video](https://www.tiktok.com/@desidezdez/video/6848395743808457990) where I emailed 1,700 colleges asking for a free t-shirt.

## Setup
Download the files in this repository by either cloning the repo or downloading as a .zip file. 

The emails are sent using a jupyter notebook. Ensure you have the following packages installed:
 * pandas
 * smtplib
 * ssl
 * email
 * getpass

If any of these are not already installed, you can get them using pip
```
pip install PKG_NAME
```

Lastly, you need to allow access to third-party apps on the email account you are using. For Gmail accounts, go to Settings > Accounts and Import > Other Google Account settings.  Under Security, scroll down and enable access for less secure apps. This setting is required to enable SMTP access.


## Personalize the emails
The files `email_text.txt` and `email_html.html` contain the body of the emails that will be sent. Open them and change the placeholder values (`FIRST_NAME`, `LAST_NAME`, `SCHOOL_NAME`, `ADDRESS`) to the names and address you would like to use. You can use a fake name and school if you'd like, but whatever address you use is the one where any shirts you get will be mailed to.

## Send the emails
Open the jupyter notebook `send_emails.ipynb`. This is where the code to run the code is. No editing or coding is required. By running all cells, you will be prompted to input the email address you wish to send the emails from, and the associated password.

In the 5th cell, there is code commented out. This line removes the *University of Delaware* from the email list. If you would like, you can un-comment this line of code and enter the school you attend (if you are in college) if you would like to exculde them from the list.

The code should start running. Due to limits in the number of emails that can be sent at a time, you may have to execute the last cell over multiple days. The variable `emails_df` contains all the admissions emails. If an error occurs, it will automatically update to remove those addresses that successfully sent. This will allow you to run the cell multiple times without sending duplicate emails to the same school. However, if your runtime resets in between executions this will also reset all saved progress.