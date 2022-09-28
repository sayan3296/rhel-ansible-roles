# system_update role

[![License: GPLv3](https://img.shields.io/badge/license-GPLv3-brightgreen.svg)](https://www.gnu.org/licenses/gpl-3.0)

Please see the collection main page for a higher level description.

## Configuration

Below are the role default values from defaults/main.yml:

<pre>
---
# Reboot policy after applying updates
# never - never reboot even if updates would require reboot
# when_needed - reboot only when needed (using needs-restarting)
# when_updated - reboot if updates were installed
# always - always reboot even if no updates were installed
system_update_reboot_policy: when_needed

# Set true to send a report after updating packages
system_update_report: true

# Default recipient email address for the report if no
# host-specific variable 'email' set in the inventory.
system_update_report_default_recipient: root@localhost

# Attach PDF version of the report
# PDFs will be generated on the control host using
# utilities from enscript and ghostscript packages
system_update_report_pdf: false

# Preamble text to include in all generated PDFs
# <HOST> will be replaced with inventory hostname
# <OSREL> will be replaced with OS release name
# <DATE> will be replaced with patching date/time
# <REBOOT> will be indicate reboot, true or false
system_update_report_pdf_preamble: |
    System Update Report
    
    
    Server: <HOST>
    Patch date: <DATE>
    OS version: <OSREL>
    Server rebooted: <REBOOT>
    
    
    The following packages were updated:
</pre>

## License

GPLv3+