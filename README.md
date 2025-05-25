# CRM Log - Voice Recording MVP

**Online Access:** [http://mvpsinfo.free.nf/?i=1](http://mvpsinfo.free.nf/?i=1)

## Description
This project is an MVP of a CRM log that allows recording prospect and activity information using voice recognition in the browser. Users can dictate data for each field or use a button to dictate the entire sequence of relevant fields.

## Main Features
- Log form with fields: Status, Temperature, Name, Value, Description, Attachment, Opportunity, Task, Next Action, Time, and Contact.
- Microphone button on each field to dictate only that field.
- Main "Dictate All" button to dictate all important fields in sequence.
- Clear visual indicators at the top of the screen during dictation.
- No backend or database required.
- Only uses PHP to serve the file (no frameworks).
- Compatible with Google Chrome and Microsoft Edge.

## Requirements
- Google Chrome or Microsoft Edge (Web Speech API doesn't work in Firefox).
- Internet connection (voice API uses Google services).
- Allow microphone access when the browser requests it.
- Serve the project from `localhost` or HTTPS (don't open the file directly with `file:///`).
- Have PHP installed (for local server).

## How to Run the Project
1. Download or clone this repository to your computer.
2. Open a terminal in the project folder.
3. Run the following command to start the PHP local server:
   ```sh
   php -S localhost:8000
   ```
4. Open your browser (Chrome or Edge) and visit:
   [http://localhost:8000/index.php](http://localhost:8000/index.php)
5. Allow microphone access when the browser requests it.
6. Use the microphone buttons to dictate each field or the "Dictate All" button to dictate the complete sequence.

## Code Structure
- `index.php`: Contains the form, design, and main interface structure.
- `js/voiceRecognition.js`: Voice recognition logic, button handling, dictation sequence, and status messages.
- `README.md`: This help file.

## Notes and Recommendations
- If you see a network error, make sure you're using `localhost` and not `file:///`.
- If voice recognition doesn't work, check microphone permissions (lock icon in the address bar).
- If you have privacy extensions, VPN, or firewall, they might block the voice API.
- The MVP doesn't save data anywhere, it only shows a success alert.

## Database Connection

In local development, the database connection is made using XAMPP. For this, make sure you have the XAMPP MySQL server running and use the following configuration in your `config/database.php` file:

```php
// Example of local connection with XAMPP
define('DB_SERVER', 'localhost');
define('DB_USERNAME', 'root');
define('DB_PASSWORD', ''); // By default, no password in XAMPP
define('DB_DATABASE', 'your_database_name');

$conn = new mysqli(DB_SERVER, DB_USERNAME, DB_PASSWORD, DB_DATABASE);
if ($conn->connect_error) {
    die('Connection failed: ' . $conn->connect_error);
}
```

In production (for example, on InfinityFree), you must change these values to those provided by your hosting, as shown below:

```php
// Example of connection on InfinityFree
define('DB_SERVER', 'sql209.infinityfree.com');
define('DB_USERNAME', 'if0_39036584');
define('DB_PASSWORD', '4ydxIY4zUYjV');
define('DB_DATABASE', 'if0_39036584_bitacora_crm');

$conn = new mysqli(DB_SERVER, DB_USERNAME, DB_PASSWORD, DB_DATABASE);
if ($conn->connect_error) {
    die('Connection failed: ' . $conn->connect_error);
}
```

Make sure to upload the `config/database.php` file with the appropriate configuration according to the environment where you're going to deploy the project.

## Credits
Developed as MVP for testing voice recording functionality in CRM.