# Website Validator

A simple Python script to validate website URLs by checking their HTTP response status.

## Description

This script checks if a website is accessible by sending an HTTP GET request and verifying the response status code. It's useful for quickly testing if websites are online and responding correctly.

## Features

- ✅ Validates website URLs by checking HTTP status codes
- ✅ Handles network errors gracefully with try-catch blocks
- ✅ Includes timeout protection (10 seconds) to prevent hanging
- ✅ User-friendly input prompts and error messages
- ✅ Returns clear success/failure indicators

## Requirements

- Python 3.6 or higher
- `requests` library

## Installation

1. Clone or download this repository
2. Install the required dependency:
   ```bash
   pip install requests
   ```

## Usage

### Running the Script

```bash
python validator
```

### Interactive Mode

When you run the script, it will prompt you to enter a website URL:

```
Enter website URL (include http:// or https://): https://example.com
```

### Example Output

**For a valid website:**
```
Website https://example.com is valid.
The website is valid.
```

**For an invalid website:**
```
Website https://invalidsite123.com is not valid. Status code: 404
The website is not valid.
```

**For network errors:**
```
Error validating website https://unreachable.com: Connection timeout
The website is not valid.
```

## How It Works

1. **Input**: The script prompts for a website URL
2. **HTTP Request**: Sends a GET request with a 10-second timeout
3. **Status Check**: Checks if the response status code is 200 (OK)
4. **Result**: Returns True/False and prints appropriate messages

## Function Reference

### `validate_website(url)`

Validates a single website URL.

**Parameters:**
- `url` (str): The website URL to validate (must include http:// or https://)

**Returns:**
- `True`: If the website responds with status code 200
- `False`: If the website is unreachable or returns a non-200 status code

**Example:**
```python
from validator import validate_website

result = validate_website("https://google.com")
print(result)  # True or False
```

## Error Handling

The script handles various types of errors:

- **Connection Timeout**: 10-second timeout prevents infinite waiting
- **Network Errors**: DNS resolution failures, connection refused, etc.
- **HTTP Errors**: Non-200 status codes (404, 500, etc.)
- **Invalid URLs**: Malformed URLs or missing protocols

## Notes

- Always include `http://` or `https://` in the URL
- The script considers only status code 200 as "valid"
- Redirects (3xx codes) are handled automatically by the requests library
- The timeout is set to 10 seconds to balance responsiveness and reliability

## License

This project is open source and available under the MIT License.

## Contributing

Feel free to submit issues, fork the repository, and create pull requests for any improvements.
