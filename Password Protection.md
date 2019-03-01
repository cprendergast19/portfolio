# Password Protection

There are occasions when you will want to protect a page, folder or entire site with a password. The password can be set in the Designer or the Editor. 

[Setting Passwords using the Designer](#setting-passwords-using-the-designer)

[Setting Passwords using the Editor](#setting-passwords-using-the-editor)

[Design the Password Page](#design-the-password-page)
 

## Setting Passwords using the Designer
[Password Protect a Page using the Designer](#password-protect-a-page-in-the-designer)

[Password Protect a Folder using the Designer](#password-protect-a-folder-in-the-designer)

[Password Protect Entire Website using the Designer](#password-protect-entire-website)

### Password Protect a Page in the Designer
In order to password protect your page you need to navigate to the **Pages** tab then select the **Page** you want to password protect, now select **Settings -> Edit Page Settings**.  You will now see the Page Settings screen as show in Fig 1 below
 
 - Enable the password protection button
 - Add your password
 - Publish to selected domain
 
![Enable Password Protection](https://lh3.googleusercontent.com/a1nHaPpRFt8hAKJDfiIG489lbElJVOXX128LerCqnwjYnemUjk0lWHz6t1GcFn6-otcmUlAlbi2MDw "Fig 1.  Enable Password Protection")

You will now see the password box appear on the screen when the web page is loaded.

>**Important**: Currently, you are only able to set page level passwords on [static pages](https://university.webflow.com/glossary/static-page). Page level passwords on dynamic, CMS generated pages is coming soon.

  > **Note:** Its possible to use different passwords for each web page.
    

### Password Protect a Folder in the Designer
To add a password to a folder is very similar to adding a password to a page. First navigate to the **Folder** that you want to protect. Now select **Settings -> Edit Folder Settings**.  You will now see the Folder Settings screen as show in Fig 2 below
 
 - Enable the password protection button
 - Add your password
 - Publish to selected domain 
 
![Fig 2. Password Protect a Folder](https://lh3.googleusercontent.com/67MFwpWmUSOmO8VSlrPRXi6j-7sX0MoQo8z7NZpaBFE7PNMXOEQsNvxeZo6SFTaqfTTjTgWMwZLYbw "Fig 2. Password Protect a Folder")

### Password Protect Entire Website
To protect the entire site select **Project Settings -> General -> Set Password.** Once you've entered a password select **Publish Your Site**. The new password will override any page or folder passwords that have been configured.

> **Note:**: Website, Page and Folder password protection are **premium features**. You must have an active [hosting subscription](https://webflow.com/pricing/one-site). If you have a **Pro Plan**, site wide passwords can be set on your webflow.io staging sites. 

## Setting Passwords using the Editor
To set a **Page** or **Folder** password in the **Editor**

1. Locate the Page/Folder you wish to protect
2. Highlight the Page/Folder by hovering over it with the mouse
3. Select the settings button to the right

![Fig 3. Setting Passwords in the Editor](https://lh3.googleusercontent.com/RCcYtcnFDED2DcxfvK4yHtY607HOjAEaNopSvbi9yjw--UwJMKUtQgr9knfTW1ngMagoKUo_eeWHaA "Fig 3. Setting Passwords in the Editor")

You will now see the screen below in Fig 4. Its very similar to the Designer screen, simply click the Password protection button to enable it. Once enabled the button will update to say **ON**

![Fig 4. Enable Password](https://lh3.googleusercontent.com/sHGwXTAW3wVC2bEVaKMjOVFhVTkSPiBsSi5PnPy0taTKslgLOkwU3vE-HjLJG0a3nPaz63lnh8Pdbg "Fig 4. Enable Password")

## Design the Password Page

Its also possible to design the password page. The layout style and configuration can be edited and previewed for both scenarios i.e. correct/incorrect password. For further information see the [Password Page Tutorial](https://university.webflow.com/article/password-page)




>**Note:**  Whether or not you use password protection, your site _may_ appear in search results **but** will not be accessible without the password. Browsers will prompt to remember log-in credentials, if you allow the browser to remember them then its possible that you will not be prompted to log in on future visits to the site.
