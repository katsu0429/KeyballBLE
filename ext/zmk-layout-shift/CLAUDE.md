# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

For detailed project overview, features, and usage instructions, please refer to [README.md](README.md).

## ZMK Development Guidelines

**CRITICAL PREREQUISITES - MANDATORY BEFORE ANY IMPLEMENTATION CHANGES:**

1. **Consult the ZMK Repository Expert**: Query the Deepwiki MCP server (repoName: `zmkfirmware/zmk`) to understand the current implementation and identify potential issues.

2. **Consult the Zephyr Repository Expert**: Since ZMK is Zephyr-based, also query the Deepwiki MCP server (repoName: `zephyrproject-rtos/zephyr`) for Zephyr-specific implementation details when needed.

3. **Share Context**: Provide the MCP server with:
   - Current implementation details
   - Identified problems or requirements
   - Your proposed implementation approach

4. **Validate Implementation Strategy**: Confirm your implementation plan with the ZMK expert before proceeding.

5. **Update Documentation**: After making any changes, always update the README.md with relevant information about new features, usage instructions, or implementation status.

**Why This Process is Essential:**
- **Pre-trained Knowledge Limitations**: LLM training data may not reflect the latest ZMK architecture, APIs, or best practices
- **Build Failure Prevention**: ZMK has specific conventions and dependencies that may not be obvious from general knowledge
- **Implementation Accuracy**: The ZMK codebase has evolved significantly, and outdated approaches will likely fail

**NO ASSUMPTIONS**: Always verify current ZMK practices before implementation. What worked in older versions may not work in current releases.

**EXPERT FIRST**: Consult `zmkfirmware/zmk` and `zephyrproject-rtos/zephyr` repository experts before coding, not after encountering build failures.

## Build Verification

**MANDATORY BUILD CHECK**: After any implementation or modification, verify that the build passes by running the following command:

```bash
ZMK_CONFIG_NAME=zmk-config-roBa just --justfile ../../justfile --working-directory ../.. build roBa_R -S zmk-usb-logging
```

If build fails, fix the issue and try again until it passes.

Important: Build may take several minutes to complete. Make sure to wait for the build to finish completely before determining if the build is successful.
