# Lynis Custom Security Audits

Custom security checks developed using Bash and integrated with Lynis on Fedora Linux 43.

## Security Checks

### 1. Password Aging Policy Audit — CUST-3001

Checks password aging settings in `/etc/login.defs`:

- `PASS_MIN_DAYS`
- `PASS_MAX_DAYS`
- `PASS_WARN_AGE`

The script compares the configured values against predefined thresholds and reports PASS, WARNING, or FAIL.

### 2. Critical File Permissions Audit — CUST-3002

Checks the ownership and selected permissions of these system files:

- `/etc/passwd`
- `/etc/group`
- `/etc/shadow`
- `/etc/gshadow`
- `/etc/sudoers`

The script checks file existence, root ownership, and selected permission conditions.

## Requirements

- Fedora Linux or a compatible Linux system
- Lynis
- Bash
- Appropriate privileges to inspect system files

## Execution

The custom tests are integrated into Lynis through its custom-test file.

Run the system audit using:

```bash
sudo lynis audit system --no-colors
```

## Test Results

On the development system, the password aging audit reported one passing check and two warnings. The file permissions audit reported five passing checks.

Results may differ depending on system configuration.

## Author

Arpit Maan

## Disclaimer

These checks evaluate only the conditions implemented in the scripts. They do not replace a complete security audit. Review findings before changing system security settings.
