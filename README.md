# logging.sh

- [logging.sh](#loggingsh)
  - [Usage](#usage)
    - [1. Sourcing the Script](#1-sourcing-the-script)
    - [2. Setting the Log Level](#2-setting-the-log-level)
    - [3. Logging Messages](#3-logging-messages)
  - [Examples](#examples)
  - [Customization](#customization)
    - [Colors](#colors)
    - [Log Format](#log-format)

A simple Bash script to handle logging with different log levels and colored output.

## Usage

### 1. Sourcing the Script

Before you can use the logging functions, source this script in your Bash script:

```bash
#!/bin/bash

# Source the logging script
source /path/to/logging.sh

# Now you can use log_debug, log_info, log_warn, log_error, etc.
```

### 2. Setting the Log Level

By default, the log level is set to `INFO`. To change it, call:

```
log_set_level DEBUG
```

Supported levels are `DEBUG`, `INFO`, `WARN`, and `ERROR`.

### 3. Logging Messages

Use the provided functions to log messages at different severities:

- Debug: `log_debug "This is a debug message"`
- Info: `log_info "This is an info message"`
- Warn: `log_warn "This is a warning message"`
- Error: `log_error "This is an error message"`

## Examples

```sh
#!/bin/bash

# Source the logging script
source logging.sh

# Set log level to DEBUG to see all messages
log_set_level DEBUG

log_debug "This debug message will be shown because log level is DEBUG."
log_info "An informational message."
log_warn "Something might be wrong, but it's not critical yet."
log_error "This is a critical error message."
```

Output might look like this:

```sh
[2024-12-30 12:34:56] [DEBUG] This debug message will be shown because log level is DEBUG.
[2024-12-30 12:34:56] [INFO] An informational message.
[2024-12-30 12:34:56] [WARN] Something might be wrong, but it's not critical yet.
[2024-12-30 12:34:56] [ERROR] This is a critical error message.
```

## Customization

### Colors

Adjust the color variables if you need a different color scheme:

```
COLOR_DEBUG="\033[0;35m" # Purple, for example
COLOR_INFO="\033[0;36m"  # Cyan, for example
# etc.
```

### Log Format

Customize the log format by modifying the `log_message()` function. For example, you can change the output to JSON or a different timestamp format.
