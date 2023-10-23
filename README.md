# test-zk---port11
port11 zk
#!/bin/sh
#
# Pre-commit hook verifying that inappropriate code will not be committed.

# Colors for the terminal output
RED='\033[0;31m'
NC='\033[0m' # No Color

# Check that Rust formatting rules are not violated.
if ! cargo fmt -- --check; then
    echo -e "${RED}Commit error!${NC}"
    echo "Please format the code via 'cargo fmt', cannot commit unformatted code"
    exit 1
fi
