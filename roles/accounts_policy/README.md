# accounts_policy role

[![License: GPLv3](https://img.shields.io/badge/license-GPLv3-brightgreen.svg)](https://www.gnu.org/licenses/gpl-3.0)

Please see the collection main page for a higher level description.

## Configuration

Below are the role default values from defaults/main.yml:

<pre>
---
# Accounts, login, password, PAM policies and profiles
# All parameters are optional, unset are left untouched


# New user defaults file useradd template
# Role provided alternatives:
# * useradd_cis.j2         - CIS Level 2 - Server compliant config
# * useradd_rhel.j2        - RHEL default config
useradd_defaults_file:

# Shadow configuration file login.defs template
# Role provided alternatives:
# * login.defs_cis.j2      - CIS Level 2 - Server compliant config
# * login.defs_rhel.j2     - RHEL default config
login_defs_config_file:

# PAM login access control file access.conf template
# Role provided alternatives:
# * access.conf_rhel.j2    - RHEL default config (empty table)
login_access_config_file:

# PAM faillock configuration file faillock.conf template
# NB. Supported RHEL versions: RHEL 8+
# Role provided alternatives:
# * faillock_cis.conf      - CIS Level 2 - Server compliant config
# * faillock_rhel.conf     - RHEL default config
faillock_config_file:

# PAM password history config file pwhistory.conf template
# NB. This is supported only since RHEL 8.8 / RHEL 9.2
# NB. This is currently not compatible with oscap(8)
# Role provided alternatives:
# * pwhistory.conf_cis.j2  - CIS Level 2 - Server compliant config
# * pwhistory.conf_rhel.j2 - RHEL default config
pwhistory_config_file:

# PAM password quality config file pwquality.conf template
# Role provided alternatives:
# * pwquality.conf_cis.j2  - CIS Level 2 - Server compliant config
# * pwquality.conf_rhel.j2 - RHEL default config
pwquality_config_file:


# Either use a system provided profile (e.g., "minimal")
# or copy and use a custom one. A custom profile must be
# named as "custom/name". E.g., use "/srv/custom/strict"
# to copy the profile custom/strict from local path /srv
# NB. Supported RHEL versions: RHEL 8+
# Role provided alternatives:
# * custom/cis  -  CIS Level 2 - Server compliant profile
#                  incl. optional support for Centrify.
system_auth_profile:

# Profile parameters for "authselect select" command
# See the "authselect show 'profile'" output for details
# E.g., with "minimal" use without-nullok with-pamaccess
# With "custom/cis" the following parameters can be used:
#   with-centrify with-mkhomedir with-pamaccess with-systemd
system_auth_profile_parameters:

# Optional PAM su configuration file template
# Role provides CIS-compliant pam_d_su.j2 which enables
# Centrify support automatically if using with-centrify
system_auth_pam_d_su_file:
</pre>

## License

GPLv3+
