# AddToDroidHome
Demo code for prompting Add to Homescreen buttons

Based on Google's documentation: https://developers.google.com/web/fundamentals/app-install-banners

Because Android requires this code to be served from https, the easiest way to get this up and running is by placing it in an AWS S3 bucket, setting everything to public, and navigating to the index page's URL from Chrome on your Android device

Since Android limits how frequently you can show this prompt, the best way to test it is to<br />
-Enable this setting in Chrome: chrome://flags/#bypass-app-banner-engagement-checks<br />
-Restart chrome so that it takes effect<br />
-Hit the index page's URL<br />
-The lower banner prompt should appear on page load<br />
-If you didn't accept the initial prompt, you can also click the Trigger button to show the modal-style prompt<br />
-Once you have "installed" the app, you will have to delete it from your homepage and clear your cache before the prompt will show again<br />
-This should work out of the box for Android's Chrome, but if it is not working, you can easily troubleshoot on a desktop computer's Chrome browser -> DevTools -> Audits -> Run Audit. Chrome will show you what is broken with your PWA<br />

Some stipulations<br />
-This has only been tested on Android's Chrome browser<br />
-Google is working toward including this as a standard UI button in their "omnibox" (searchbar)<br />
-The start_url (located in manifest.json) must exist at the same origin as the site from which you "installed" the PWA
