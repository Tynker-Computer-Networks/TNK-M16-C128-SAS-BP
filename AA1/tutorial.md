Check the website for XSS vulnerability
======================
In this activity, you will check for XSS vulnerability of a website.

<img src= "https://s3-whjr-curriculum-uploads.whjr.online/32cc9d6b-881e-4321-8999-4ec328c8ca4d.gif" width = "100%" height = "50%">

Follow the given steps to complete this activity.

1. Open `index.html` in the browser.
2. Perform the Cross Site Scripting Attack by entering following lines in the feedback box:
    ```
    <script>alert('Hello! You are Hacked')</script>
    ```
    or

    ```
     <img src onerror="alert(document.cookie)">
    ```
    or
    ```
    <img src onerror="alert('Hello! You are Hacked')">
    ```

Find out the website's vulnerability.
