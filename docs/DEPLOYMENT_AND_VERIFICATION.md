# ECS Mobile Defensive Security — Deployment and Verification Standard

[← Back to the main README](../README.md)

**Status:** Proposed service procedure and customer acceptance checklist. This is not a published audit report or proof that a particular device has passed.

## 1. Before installation

- [ ] Confirm lawful ownership and authorization to configure the device.
- [ ] Confirm exact model, storage, carrier/SKU restrictions and GrapheneOS production support.
- [ ] Explain that changing the operating system typically wipes existing data.
- [ ] Review required applications, enterprise restrictions, MFA tools and eSIM/SIM needs.
- [ ] Assess the customer's threat model and prioritise practical protections.
- [ ] Agree on backup, account ownership, recovery and loss/theft procedures.
- [ ] Confirm what will and will not be included in the quoted service.

## 2. Platform installation

- [ ] Use official installation instructions and official supported builds.
- [ ] Install the selected release in a suitable trusted environment.
- [ ] Re-lock the bootloader after installation.
- [ ] Disable OEM unlocking after finishing where directed by the vendor.
- [ ] Verify installed operating system, boot state and supported attestation checks.
- [ ] Verify that security updates can be received normally.

## 3. Harden according to the approved plan

- [ ] Configure appropriate passphrase/PIN and unlock policy.
- [ ] Review auto-reboot, USB, radios, connectivity and sensitive permissions.
- [ ] Create agreed user profiles and account boundaries.
- [ ] Install only required apps and review their provenance and permissions.
- [ ] Set approved DNS, VPN and secure communications configurations.
- [ ] Verify that routing and kill-switch controls behave correctly on relevant transitions.
- [ ] Document exceptions needed to preserve customer workflows.

## 4. Functional and security validation

- [ ] Confirm basic voice/SMS, network connectivity and necessary apps.
- [ ] Validate business sign-in/MFA and any approved Google Play compatibility requirements.
- [ ] Confirm the device has a locked bootloader and the intended system is running.
- [ ] Confirm the planned profile/application restrictions are present.
- [ ] Check VPN/DNS behavior without assuming the use of a VPN ensures anonymity.
- [ ] Check customer-approved backup and recovery arrangements.
- [ ] Record unresolved limitations and receive customer acceptance of exceptions.

## 5. Handover

- [ ] Provide a non-sensitive summary of the configuration and exceptions.
- [ ] Explain software updates, app installation rules and everyday operating precautions.
- [ ] Explain device loss and suspected-compromise steps.
- [ ] Confirm the customer retains credentials and recovery material unless a different custodial arrangement is specifically documented.
- [ ] Confirm maintenance contacts, coverage, support life and data-erasure caveats.

## 6. Evidence and privacy

Customer validation records should be stored privately, with no publication of serial numbers, keys, account identifiers, network details, contact information or security exceptions. If screenshots or logs are used, collect only what is necessary and handle it according to customer consent and agreed retention policy.

## 7. Related

- [Security Architecture](SECURITY_ARCHITECTURE.md)
- [Service Scope and Maintenance](SERVICE_SCOPE_AND_MAINTENANCE.md)
- [GrapheneOS installation guidance](https://grapheneos.org/install/web)

[← Back to the main README](../README.md)
