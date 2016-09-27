# XKEYSCORE

## Purpose

The purpose of this project is to create a [Kickstart](https://github.com/rhinstaller/pykickstart/blob/master/docs/kickstart-docs.rst) file to perform the initial installation and configuration on `XKEYSCORE`.

During installation, the system will be configured to achieve compliance with as many controls in the below [security profiles](https://www.open-scap.org/security-policies/choosing-policy/) as is feasible.

- [U.S. Government Commercial Cloud Services (C2S)](http://static.open-scap.org/ssg-guides/ssg-rhel7-guide-C2S.html)
- [CNSSI 1253 Low/Low/Low Control Baseline](http://static.open-scap.org/ssg-guides/ssg-rhel7-guide-nist-cl-il-al.html)
- [Common Profile for General-Purpose Systems](http://static.open-scap.org/ssg-guides/ssg-rhel7-guide-common.html)
- [Criminal Justice Information Services (CJIS) Security Policy](http://static.open-scap.org/ssg-guides/ssg-rhel7-guide-cjis-rhel7-server.html)
- [Payment Card Industry - Data Security Standard (PCI-DSS) v3](http://static.open-scap.org/ssg-guides/ssg-rhel7-guide-pci-dss.html)
- [STIG for Red Hat Enterprise Linux 7 Server](http://static.open-scap.org/ssg-guides/ssg-rhel7-guide-stig-rhel7-server-upstream.html)
- [Standard System Security Profile](http://static.open-scap.org/ssg-guides/ssg-rhel7-guide-standard.html)
- [United States Government Configuration Baseline (NIAP OSPP v4.0, USGCB, STIG)](http://static.open-scap.org/ssg-guides/ssg-rhel7-guide-ospp-rhel7-server.html)

At first boot the installed host should be "production ready".

## Mission Accomplished

This project is considered complete and it is likely that no further development will occur.

I can't claim 100% passing rate on all checks/controls as that will simply not be possible, for various reasons.

One reason is that, like all software, the [OpenSCAP](https://www.open-scap.org/) [software](https://github.com/OpenSCAP/openscap) is not perfect. Even when a host is configured according to these profiles, false positives are still reported. In at least two cases, the guidance and suggested remediation differ (such as the sysctl for secure_redirects).

At other times, the remediation for one control causes a subsequent failure for another control. For example, in order to ensure that all log files are only readable by root, one must modify `/etc/rc.d/rc.local` to change the permissions of `/var/log/boot.log` every time the system boots up. This causes a "fail" on the control that verifies that the MD5 checksum of all files matches the MD5 checksum when they were initially installed.

Hence, I have come to the conclusion that "this is as good as it's gonna get" and consider this project "complete".

The OpenSCAP Project is an awesome resource and they have obviously put a tremendous amount of work into it. It still has a long way to go, however, and I look forward to the day when it can be relied upon to generate accurate scan results.

In the very near future, I will be creating a new kickstart configuration file -- for CentOS, instead of RHEL -- to supercede this. It will follow many (or perhaps even most) of the same controls from the various security profiles but will instead focus on settings and values that are "sane" and "sensible" (e.g. an account lockout period of one week after three failed login attempts seems a bit "over the top" in the average enterprise environment). Stay tuned to this space; I'll add a link to it here.
