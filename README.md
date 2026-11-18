# microsoft-defender-endpoint-hardening
Windows endpoint security assessment and Microsoft Defender hardening project
# Microsoft Defender Endpoint Security Hardening

## Project Overview
Independent cybersecurity lab assessing and strengthening Windows endpoint security using Microsoft Defender, PowerShell, Windows Firewall, and BitLocker.

## Tools Used
- Microsoft Defender Antivirus
- Windows PowerShell
- Windows Firewall
- BitLocker
- Windows Security
- EICAR Antivirus Test File

## Security Assessment
- Verified antivirus, real-time protection, and behavior monitoring were enabled.
- Confirmed Domain, Private, and Public firewall profiles were enabled.
- Verified BitLocker full-disk encryption, TPM and recovery password protectors, and recovery key backup.
- Reviewed Controlled Folder Access configuration in Audit Mode.

## Security Remediation
Identified PUA protection operating in Audit Mode (2). Enabled blocking and verified PUAProtection changed to 1 using PowerShell.

## Threat Detection Test
Tested Microsoft Defender using the harmless EICAR antivirus test file. Confirmed detection of Virus:DOS/EICAR_Test_File and reviewed removal and quarantine actions in Windows Security Protection History.

## Final Results
- Microsoft Defender Antivirus: Enabled
- Real-time protection: Enabled
- Behavior monitoring: Enabled
- Windows Firewall: All three profiles enabled
- PUA protection: Enabled
- Controlled Folder Access: Audit Mode (intentionally retained)
- BitLocker: Fully encrypted, protection on
- EICAR detection: Successful

## Skills Demonstrated
Endpoint security assessment, PowerShell auditing, antivirus detection validation, security configuration remediation, BitLocker verification, and technical documentation.

## Security Note
This project used a harmless antivirus test file. Screenshots and reports are sanitized to exclude sensitive information.
