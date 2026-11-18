# Microsoft Defender Endpoint Security Assessment Report

**Project Type:** Independent Cybersecurity Lab  
**Assessment Date:** November 18, 2026  
**Environment:** Windows Endpoint  
**Tools:** Microsoft Defender Antivirus, PowerShell, Windows Firewall, BitLocker, Windows Security, EICAR

## 1. Executive Summary

Conducted a Windows endpoint security assessment to evaluate antivirus protection, host firewall settings, disk encryption, potentially unwanted application (PUA) protection, and Controlled Folder Access.

Identified PUA protection operating in Audit Mode, enabled blocking, and verified the remediation using PowerShell. Validated antivirus detection using the harmless EICAR test signature.

## 2. Assessment Objectives

- Verify antivirus and real-time protection.
- Review Windows Firewall profiles.
- Verify BitLocker encryption and recovery readiness.
- Identify and remediate security configuration weaknesses.
- Test antivirus detection and response.
- Document the final security configuration.

## 3. Security Findings

| Control | Verified Result |
|---|---|
| Microsoft Defender Antivirus | Enabled |
| Real-Time Protection | Enabled |
| Behavior Monitoring | Enabled |
| Antivirus Signatures | Updated November 18, 2026, 4:50 AM |
| Domain Firewall | Enabled |
| Private Firewall | Enabled |
| Public Firewall | Enabled |
| PUA Protection | Enabled (1) |
| Controlled Folder Access | Audit Mode (2) |
| BitLocker Encryption | Fully encrypted (100%) |
| BitLocker Protection | On |
| TPM and Recovery Password Protectors | Present |
| Recovery Key Backup | Verified in Microsoft account |

## 4. PUA Protection Remediation

**Initial Finding:** PUAProtection was configured in Audit Mode (2), which records detections without enforcing blocking.

**Remediation Command:**

```powershell
Set-MpPreference -PUAProtection Enabled
```

**Verification Command:**

```powershell
Get-MpPreference | Select-Object PUAProtection
```

**Verified Result:** PUAProtection = 1.

**Status:** Remediated.

## 5. Antivirus Detection Validation

Performed controlled antivirus testing using the harmless EICAR test signature.

**Detection Results:**

- Threat Name: Virus:DOS/EICAR_Test_File
- Threat ID: 2147519003
- Severity ID: 5
- Protection History recorded threat-blocking events.
- Removal and quarantine actions were observed.

**Result:** PASS — EICAR detection and protective response verified.

## 6. Windows Firewall Verification

Executed:

```powershell
Get-NetFirewallProfile | Select-Object Name, Enabled
```

**Results:**

- Domain: True
- Private: True
- Public: True

All three firewall profiles were enabled at the time of assessment.

## 7. BitLocker Encryption Verification

Verified the system drive was fully encrypted (100%) with BitLocker protection enabled.

Confirmed the presence of TPM and recovery password protectors and verified that the recovery key was backed up to the associated Microsoft account.

Recovery passwords are not included in this report or public evidence.

## 8. Controlled Folder Access Decision

Controlled Folder Access was verified in Audit Mode (2).

This configuration was intentionally retained pending application compatibility review. Audit Mode does not enforce blocking.

**Recommendation:** Review audit events and application compatibility before considering enforcement.

## 9. Final Assessment

The assessment verified enabled antivirus, real-time protection, behavior monitoring, Windows Firewall profiles, and BitLocker encryption.

PUA protection was changed from Audit Mode to blocking mode and verified.

The EICAR test confirmed Microsoft Defender detection and protective response.

**Conclusion:** Completed endpoint security assessment, targeted configuration remediation, and controlled antivirus detection validation.

## 10. Skills Demonstrated

- Endpoint Security Assessment
- Microsoft Defender Administration
- PowerShell Security Auditing
- Antivirus Detection Validation
- Windows Firewall Assessment
- BitLocker Encryption Verification
- Security Configuration Remediation
- Technical Documentation

**Security Note:** This independent lab used the harmless EICAR test signature rather than live malware. Sensitive recovery information is excluded from public documentation.
