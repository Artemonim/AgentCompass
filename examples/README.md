# Usage Examples

This directory contains practical examples of how Agent Compass transforms AI-assisted development interactions.

## Example Scenarios

### 1. Basic Task Assignment

**Before Agent Compass:**

```
You: "Create a login system"
AI: [Generates basic code without structure or security considerations]
```

**After Agent Compass:**

```
You: "Create a login system"
AI: [Generates secure, well-structured code with proper error handling]

Changes Made:
- Created UserAuthService class with secure password hashing
- Implemented login/logout endpoints with input validation
- Added JWT token generation and verification
- Created middleware for protected routes
- Added rate limiting for login attempts

Manual Changes Required:
- Replace JWT_SECRET_KEY placeholder with actual secret key
- Configure database connection string in config file
- Add authentication routes to main application router

Special Attention Required:
- Review JWT token expiration time (currently set to 24 hours)
- Verify bcrypt salt rounds meet security requirements (currently 12)
- Consider implementing refresh token mechanism for better security
```

### 2. Architecture Evaluation

**Before Agent Compass:**

```
You: "Use microservices for this project"
AI: [Blindly implements microservices without considering context]
```

**After Agent Compass:**

```
You: "Use microservices for this project"
AI: I'll evaluate this architectural approach for your specific context.

[Provides implementation if appropriate]

Rationale for Significant Deviations:
While microservices offer scalability and service isolation benefits, for a team of 2-3 developers with moderate traffic expectations, a well-structured monolith with clear module boundaries might be more appropriate. This approach provides:
- Simpler deployment and operational overhead
- Easier debugging and transaction management
- Lower infrastructure costs
- Faster development iteration

However, if you anticipate rapid scaling, have specific service isolation requirements, or plan to grow the team significantly, I can proceed with the microservices approach.
```

### 3. Security-First Development

**Before Agent Compass:**

```
You: "Add file upload functionality"
AI: [Creates basic file upload without security considerations]
```

**After Agent Compass:**

```
You: "Add file upload functionality"
AI: [Implements secure file upload with comprehensive validation]

Changes Made:
- Created FileUploadService with file type validation
- Implemented file size limits and virus scanning integration
- Added secure file storage with randomized names
- Created upload progress tracking
- Added file metadata validation

Manual Changes Required:
- Configure MAX_FILE_SIZE in environment variables
- Set up virus scanning service endpoint
- Configure secure file storage location
- Add ALLOWED_FILE_TYPES to configuration

Special Attention Required:
- File upload endpoint is vulnerable to path traversal attacks - implement proper sanitization
- Consider implementing file quarantine before virus scanning
- Review file storage permissions and access controls
- Implement file cleanup for failed uploads
```

## Installation Verification

After installing Agent Compass rules, test with this simple request:

```
Create a simple "Hello World" web server
```

You should receive:

-   Well-structured code with proper error handling
-   Clear comments using Better Comments style
-   Security considerations (even for simple examples)
-   Detailed report of changes made
-   Instructions for any manual configuration needed

## Language-Specific Examples

### Python Example

```python
# * Main application entry point
import logging
from flask import Flask, jsonify
from typing import Dict, Any

# * Configuration variables
HOST = "127.0.0.1"
PORT = 5000
DEBUG_MODE = False

# * Initialize Flask application
app = Flask(__name__)

@app.route("/")
def hello_world() -> Dict[str, Any]:
    """
    Returns a simple greeting message.

    Returns:
        Dict[str, Any]: JSON response with greeting message
    """
    try:
        return jsonify({"message": "Hello, World!", "status": "success"})
    except Exception as e:
        # ! Log error for debugging
        logging.error(f"Error in hello_world endpoint: {str(e)}")
        return jsonify({"error": "Internal server error"}), 500

if __name__ == "__main__":
    # * Configure logging
    logging.basicConfig(level=logging.INFO)

    # * Start the application
    app.run(host=HOST, port=PORT, debug=DEBUG_MODE)
```

### JavaScript Example

```javascript
/**
 * Simple Express.js Hello World server
 * @author Agent Compass
 */

// * Configuration variables
const HOST = process.env.HOST || "localhost";
const PORT = process.env.PORT || 3000;

// * Import required modules
const express = require("express");
const helmet = require("helmet");

// * Initialize Express application
const app = express();

// * Security middleware
app.use(helmet());

// * JSON parsing middleware
app.use(express.json({ limit: "10mb" }));

/**
 * Hello World endpoint
 * @route GET /
 * @returns {Object} JSON response with greeting
 */
app.get("/", (req, res) => {
    try {
        res.json({
            message: "Hello, World!",
            status: "success",
            timestamp: new Date().toISOString(),
        });
    } catch (error) {
        // ! Log error for debugging
        console.error("Error in hello endpoint:", error);
        res.status(500).json({ error: "Internal server error" });
    }
});

// * Start server
app.listen(PORT, HOST, () => {
    console.log(`Server running at http://${HOST}:${PORT}`);
});
```

## Best Practices Demonstrated

1. **Better Comments Style**: Notice the `*`, `!`, `?`, and `TODO:` prefixes
2. **A-temporal Comments**: Comments describe what code _does_, not what it _used to do_
3. **Security Considerations**: Even simple examples include basic security measures
4. **Error Handling**: Comprehensive error handling with proper logging
5. **Configuration Variables**: All configurable values at the top
6. **Input Validation**: Proper validation of all inputs
7. **Documentation**: Clear docstrings and comments in appropriate styles
