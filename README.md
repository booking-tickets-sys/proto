# Protocol Buffer Setup

This directory contains Protocol Buffer (`.proto`) files for the booking tickets system, along with a Makefile for formatting and validation.

## Files

- `ticket-svc.proto` - Ticket service definitions
- `user-svc.proto` - User service definitions
- `Makefile` - Build and validation commands

## Prerequisites

Before using the Makefile, you need to install the required tools:

### macOS
```bash
make install
```

### Manual Installation
If you prefer to install manually:

```bash
# Install Protocol Buffers compiler
brew install protobuf

# Install Buf CLI tool
brew install bufbuild/buf/buf
```

## Available Commands

### Install Dependencies
```bash
make install
```
Installs `protoc` and `buf` using Homebrew.

### Format Protocol Buffer Files
```bash
make format
```
Formats all `.proto` files using `buf` for consistent styling.

### Validate Protocol Buffer Files
```bash
make validate
```
Validates syntax and semantic correctness of all `.proto` files.

### Check Formatting and Validation
```bash
make check
```
Checks if files are properly formatted and validates their syntax.

### Complete Workflow
```bash
make all
```
Runs the complete workflow: format → validate → check.

## Quick Start

1. **Install dependencies** (if not already installed):
   ```bash
   make install
   ```

2. **Run complete validation**:
   ```bash
   make all
   ```

## Service Definitions

### Ticket Service (`ticket-svc.proto`)
Defines the ticket purchasing service with:
- `PurchaseTicket` RPC for buying tickets
- Request/response messages for ticket operations
- Status enumeration for purchase results

### User Service (`user-svc.proto`)
Defines user authentication and management with:
- User registration and login
- Token management (access/refresh tokens)
- User profile operations
- Token cleanup functionality

## Development Workflow

1. **Before committing changes**:
   ```bash
   make all
   ```

2. **If you only want to format**:
   ```bash
   make format
   ```

3. **If you only want to validate**:
   ```bash
   make validate
   ```

## Troubleshooting

### "buf: No such file or directory"
Run `make install` to install the required dependencies.

### Validation errors
Check your `.proto` files for:
- Syntax errors
- Missing semicolons
- Incorrect field numbers
- Invalid import statements

### Formatting issues
Run `make format` to automatically fix formatting issues.

## Dependencies

- **protoc** - Protocol Buffers compiler
- **buf** - Modern Protocol Buffer tool for linting and formatting

## Contributing

When adding new `.proto` files or modifying existing ones:

1. Add your changes
2. Run `make all` to ensure everything is correct
3. Commit your changes

This ensures consistent formatting and validates that all Protocol Buffer definitions are syntactically correct. 