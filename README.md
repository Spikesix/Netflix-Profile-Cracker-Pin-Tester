# Netflix-Profile-Cracker-Pin-Tester
Αutomatically unlock Netflix profiles by systematically testing all possible 4-digit PIN combinations using a browser automation script.



## Before You Begin

Make sure you have:

- A valid Netflix account with login credentials
- A locked profile you want to access
- A `codes.txt` file containing PINs (`0000–9999`)

#### `You should download the Codes.txt and the Script.txt.`



## Step 1: Log Into Netflix

1. Open your web browser (Chrome / Firefox / Edge).
2. Go to `https://www.netflix.com`.
3. Log in with your email and password.
4. You should see the profile selection screen.


## Step 2: Select the Locked Profile
 
1. Click on that profile.
2. A PIN entry screen will appear asking for the 4-digit code.
3. **Do not try any codes manually** — leave this screen open.


## Step 3: Open Developer Console

1. Press **F12** on your keyboard (or **Ctrl + Shift + I** for Chrome).
2. Click on the **Console** tab.
3. You should see a blank area where you can type commands.


## Step 4: Paste and Execute the Code

1. Copy the entire script code provided.
2. Paste it into the Console area.
3. Press **Enter** to run the script.
4. A file selection window should appear immediately.



## Step 5: Load Your PIN Codes

1. Click **Choose File** or **Open** in the popup window.
2. Navigate to where your `codes.txt` file is saved.
3. Select the file and click **Open**.
4. The console will display:

```
🔢 Loaded codes: 10000
```
(or however many PINs are in the file).



## Step 6: Let It Run

The script will automatically:

- Click on the profile if needed
- Start testing PINs one by one
- Display progress in the console

Example output:

```
[1] pin=0000 success=false latency=1450ms
[2] pin=0001 success=false latency=1380ms
[3] pin=0002 success=false latency=1420ms
...
```


## Important Timing Information

- If the PIN starts with low numbers (e.g. `1XXX`, `2XXX`), it may be found within minutes.
- If the PIN starts with high numbers (e.g. `8XXX`, `9XXX`), it may take several hours.
- Average testing speed: approximately **1 PIN per second**.



## When the Correct PIN Is Found

```
✅ Success! PIN: 1234
```

- The script stops automatically.
- Netflix proceeds to the profile.
- You now have access to the locked profile.



## Expected Completion Times

- Best case (`0000`): less than 5 seconds
- Average case (`5000`): about 1.5 hours
- Worst case (`9999`): about 2.5 hours



## Safety Features

- Rate limiting: 1 second between attempts
- Automatic logging to `logs.jsonl`
- Error recovery if a PIN attempt fails
- Automatic stop when the correct PIN is found



## Troubleshooting

### File does not load

- Ensure `codes.txt` has one PIN per line
- Make sure the file is not empty
- Try selecting the file again

### Script stops working

1. Refresh the Netflix page (**F5**).
2. Log in again.
3. Restart from **Step 3**.

### "Too many attempts" message

- Wait 30 minutes
- Continue from where it stopped (remove tested PINs from `codes.txt`)
- Increase delay in the script (`RATE_MS = 2000`)


## Notes

- The script simulates real keyboard input.
- Network requests are monitored to detect successful authentication.
- DOM changes are tracked as a fallback method.
- Always download the `logs.jsonl` file for reference.


## Final Result

The correct 4-digit PIN will eventually be found. Leave your computer running and check periodically. Once found, access to the locked profile is granted.



## Disclaimer

This tool is for educational purposes only and should be used only on accounts you own or have explicit permission
