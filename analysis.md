# SSH Brute Force Attack Analysis

## Overview
This project analyzes SSH logs to identify a brute-force attack, successful compromise, and privilege escalation activity.

## What Happened
- Multiple SSH login attempts from 45.33.32.156 targeting invalid users (admin, guest, test)
- Followed by a successful login to the backup account
- A session was opened for user backup
- The attacker used sudo to execute commands as root

## Why It Matters
This activity is consistent with a successful brute-force attack, where repeated login attempts led to unauthorized access.

The use of sudo indicates privilege escalation activity, which poses a risk to system integrity and potentially sensitive data.

## Evidence
- Failed login attempts from 45.33.32.156 (admin, guest, test)
- “Accepted password for backup from 45.33.32.156”
- /usr/bin/id
- /bin/bash

## Recommended Actions
- Block or blacklist 45.33.32.156 at network controls
- Disable the backup account and reset credentials
- Review logs for additional activity
- Escalate the incident according to policy
