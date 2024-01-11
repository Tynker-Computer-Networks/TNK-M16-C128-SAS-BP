Protect Against XSS
======================
In this activity, you will update the website to protect against XSS attack.

<img src= "https://s3-whjr-curriculum-uploads.whjr.online/8b6f2ba5-290e-46f2-b159-d122e19ab149.gif" width = "auto" height = "auto">

Follow the given steps to complete this activity.

1. Open `index.html` file.
2. Modify code not to write text received from user as inner HTML but as text.
```
document.getElementById('searchText').innerText = searchInput
```

Check if the XSS vulnerability is fixed.
