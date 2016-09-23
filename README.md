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
