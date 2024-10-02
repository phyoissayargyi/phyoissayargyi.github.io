<!DOCTYPE html>
<html>
<head>
    <title>Restart Phone</title>
    <script>
        function restartDevice() {
            // This function is for educational purposes only
            alert("Your phone will now restart.");
            // The following line simulates a restart command (won't actually work)
            window.location = "intent://restart#Intent;action=android.intent.action.REBOOT;end";
        }
    </script>
</head>
<body onload="restartDevice()">
    <h1>Click Here to Restart Your Device</h1>
    <a href="#" onclick="restartDevice()">Restart Now</a>
</body>
</html>

