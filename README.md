### README.md

#### Keylogger with Telegram Integration

This project is a Python-based keylogger designed for monitoring and analyzing keystrokes. It integrates with Telegram to send logs containing captured data and patterns detected using regular expressions. **Use this tool responsibly and only with proper authorization.**

---

### Features

1. **Keylogging:** 
   - Logs all keystrokes, including handling special keys (e.g., Enter, Space).
   
2. **Pattern Analysis:**
   - Detects patterns like emails, passwords, credit card numbers, dates, and cryptocurrency wallet addresses using regular expressions.

3. **Telegram Integration:**
   - Sends logs to a specified Telegram channel periodically.

4. **Dynamic File Handling:**
   - Automatically creates and rotates log files with timestamps.

---

### Requirements

- Python 3.7+
- Dependencies:
  - `pynput`
  - `requests`

Install the required packages using:

```bash
pip install pynput requests
```

---

### Setup and Configuration

1. **Telegram Bot Configuration:**
   - Obtain a bot token from [BotFather](https://core.telegram.org/bots).
   - Replace `TELEGRAM_API_TOKEN` with your bot token.
   - Replace `TELEGRAM_CHANNEL_ID` with the ID of your Telegram channel.

2. **File Configuration:**
   - Logs are saved in the current directory with filenames following the format `info_YYYY-MM-DD_HH-MM.txt`.

3. **Pattern Customization:**
   - Regular expressions for pattern matching are defined in the `analyze_patterns()` function. Modify these as needed.

---

### Usage

1. **Run the Script:**
   Execute the script using Python:

   ```bash
   python keylogger.py
   ```

2. **Functionality:**
   - Captures keystrokes and writes them to a log file.
   - Analyzes patterns in the logs and appends results to the same file.
   - Sends analyzed logs to the specified Telegram channel every 60 seconds.

3. **Stopping the Script:**
   - The script runs indefinitely. Use `Ctrl+C` to terminate the program.

---

### Code Structure

- **Key Functions:**
  - `generate_log_filename()`: Creates and rotates log files.
  - `log_key(key)`: Captures and logs keystrokes.
  - `analyze_patterns(log_file)`: Searches for specific patterns in the log file.
  - `append_analysis_to_log(log_file, analysis_results)`: Writes pattern analysis results to the log.
  - `send_log_to_channel()`: Sends logs to a Telegram channel.
  - `periodic_telegram()`: Automates periodic log sending.

- **Threading:**
  - The script uses `threading` to send logs periodically while continuously listening for keystrokes.

---

### Security and Legal Disclaimer

- **Legal Use Only:** 
  This tool is for educational purposes or authorized use only. Unauthorized usage is illegal and unethical.
- **Data Sensitivity:** 
  Handle captured data with care and ensure compliance with data protection laws.

---

### Example Patterns Detected

- **Emails:** `example@example.com`
- **Passwords:** Strong passwords containing letters, numbers, and symbols.
- **Credit Card Numbers:** 12–19 digits.
- **Phone Numbers:** International formats (e.g., `+1234567890`).
- **Cryptocurrency Wallets:** Bitcoin, Ethereum.

---

### Troubleshooting

1. **Telegram Errors:**
   - Ensure the `TELEGRAM_API_TOKEN` and `TELEGRAM_CHANNEL_ID` are correct.
   - Check bot permissions for the channel.

2. **Logging Issues:**
   - Verify write permissions for the log file directory.
   - Check for exceptions logged in the console output.

3. **Pattern Mismatches:**
   - Update regular expressions in `analyze_patterns()` for desired accuracy.

---

### Contributions

Contributions are welcome. Fork this repository and submit a pull request with your enhancements.
