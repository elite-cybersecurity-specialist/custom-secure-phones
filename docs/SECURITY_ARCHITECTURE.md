# ECS Mobile Defensive Security — Architecture and Threat Model

[← Back to the main README](../README.md)

**Status:** Proposed client-facing architecture; controls are tailored to each engagement and verified when implemented.

## 1. Purpose

The goal of this architecture is to reduce unnecessary attack surface, make unauthorized exploitation and access more difficult, compartmentalize sensitive activities and retain a maintainable device. The security of the underlying Pixel/GrapheneOS platform is provided by its developers; ECS's proposed role is configuration engineering, integration, validation and handover.

## 2. Trust boundaries

| Boundary | Protection objective | Operational consideration |
|---|---|---|
| Hardware / firmware / OS | Supported device, verified boot, official updates | No unsupported firmware or casually unlocked bootloader |
| Device owner / unlock method | Encrypted at-rest data, robust authentication | Recovery usability, coercion risk, owner training |
| Apps / permissions | Restrict unnecessary data access and interoperability | Some apps require exceptions |
| User profiles / identities | Reduce cross-contamination between activities | Notifications and inter-profile workflows may be affected |
| Network / DNS / VPN | Enforce agreed routing, minimize avoidable leaks | VPNs do not conceal cellular identity from carriers |
| Contacts / communications | Choose E2EE tools, verify correspondent identities | Endpoint compromise and human error remain relevant |
| Backups / replacement | Recover service safely without uncontrolled copies | No backup method is immune to availability or confidentiality risks |

## 3. Assessed threat scenarios

1. **Lost or stolen device:** mitigate opportunistic access through device encryption, strong unlock credentials, automatic reboot and appropriate USB/physical controls.
2. **Untrusted or compromised app:** constrain permissions and storage/contact exposure; isolate selected usage into distinct profiles.
3. **Malicious web content or exploitation attempts:** benefit from GrapheneOS exploit mitigations and a hardened browser; keep components updated.
4. **Exposed accounts or reused identities:** review authentication, account segregation and recovery, not only phone settings.
5. **Untrusted local networks:** evaluate VPN, DNS, wireless settings and leak/failure behavior.
6. **Sensitive communication interception:** choose suitable encrypted tools; verify contacts and account security.
7. **Recovery from suspicious behavior or change:** keep restoration/reinstall procedures and customer-owned recovery material.

These are scenarios to assess—not claims that every threat can be eliminated.

## 4. Proposed technical layers

### Layer A — Hardware and authenticity

- Confirm exact device model and bootloader-unlock eligibility.
- Verify it appears on the official [GrapheneOS supported-device list](https://grapheneos.org/faq#supported-devices).
- Install an official production release using its [published installation procedure](https://grapheneos.org/install/web).
- Re-lock the bootloader; use available official verification and hardware attestation procedures where appropriate.
- Record update and supported-lifetime considerations.

### Layer B — Operating-system and physical configuration

- Select strong authentication appropriate for device and owner.
- Apply auto-reboot and supported USB/device controls when consistent with customer requirements.
- Review location, radios and hardware permissions on a real use-case basis.
- Avoid rooting or unnecessary modifications that undermine verified boot and platform updates.

### Layer C — Applications, profiles and accounts

- Install required applications from trusted sources; evaluate the need for sandboxed Google Play individually.
- Review per-app network, media, contacts, camera, microphone and location permissions.
- Design profile separation for approved categories of use and test required interoperability.
- Keep account enrollment and recovery under customer control unless agreed otherwise.

### Layer D — Networks and communications

- Configure approved VPN and DNS settings where relevant; test expected failure behavior.
- Consider Tor only for well-defined use cases, not as a blanket anonymity guarantee.
- Establish communication-app selection and correspondent identity verification.
- Document incompatibilities and necessary exceptions.

### Layer E — Operations and recovery

- Confirm applications, voice, messages and essential services function.
- Record approved settings and deviations without exposing passwords, private keys or customer data in public repositories.
- Educate the device owner about routine updates and signs of account/device compromise.
- Provide the covered maintenance route described in the written service agreement.

## 5. What is not promised

This architecture does not guarantee invisibility, anonymity from mobile carriers, perfect resistance against high-end exploitation, interception-proof endpoint use or the prevention of social engineering. Data migration, backups and app compatibility may require trade-offs.

## 6. Reference materials

- [GrapheneOS features](https://grapheneos.org/features)
- [GrapheneOS support FAQ](https://grapheneos.org/faq)
- [GrapheneOS official installation](https://grapheneos.org/install/web)
- [GrapheneOS usage](https://grapheneos.org/usage)

[← Back to the main README](../README.md)
