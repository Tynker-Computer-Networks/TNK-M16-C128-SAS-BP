Protect Against XSS
======================
In this activity, you will update the Feedback App to protect against the XSS attack.

<img src= "https://s3-whjr-curriculum-uploads.whjr.online/16cd5cda-1ef9-4fde-aa11-6065889991d9.gif" width = "auto" height = "auto">

Follow the given steps to complete this activity.

1. Open `feedback.html` file of the `Flask Feedback App/templates`.
2. Modify code not to write text received from user as inner HTML but as text.
```
var listItem = $('<li>');

var feedbackInfo = $('<div>').addClass('feedback-info');
feedbackInfo.append($('<strong>').text('Name: '), $('<span>').text(feedback[0]));
feedbackInfo.append($('<br>'));
feedbackInfo.append($('<strong>').text('Email: '), $('<span>').text(feedback[1]));

listItem.append(feedbackInfo);
listItem.append($('<p>').text(feedback[2]));
```
3. Run HackerDashboard app.
4. Run the Feedback app and perform XSS attack by adding following script:
```
<script src="http://127.0.0.1:5000/script"></script>
```

Check if the XSS vulnerability is fixed.
