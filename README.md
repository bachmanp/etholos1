# etholos1
This is an initial commit for the X.509v3/X.500 c=US Healthcare identity and informatics Directory. While the "Directory" and related PKI is well established, is a critical (if not well understood) part of network infrastructure, and thus has been extensively tested, and documented in security realms; this particular repository use case will focus on generating soverign patient identity using experimental protocols funded by recent research at Department of Homeland Security to develop "sovereign identity" with DKMS. 

The point is to augment the quality and depth of the current PKI under c=US, or country equals US, for which I have been a manager and developer since the 1990s. There are a number of related efforts which I will list here to improve the PKI for the end user. 

Saving costs by adopting a National Patient Identifier

The HIPAA legislation described and  encouraged a NPI, but after the legislation was passed, it appeared that a centralized database would be likely be hacked. As such Congress decided to pass legislation that (still currently) forbids HHS from funding an NPI. 

Using SSN for a NPI substitute, or patient matching algorithms has been similarly problematic. So (uniquely), here in the US, there are few options.

1. An internal government solution of patient identity (established recently by CMS) to mitigate Identity Theft for seniors. 
2. An ASTM/ANSI standard for Patient ID, written by Barry Hieb, and implemented by his company which issues Public and Private Patient Identifiers https://www.gpii.info/
3. As a patient of a hosptital or care organization that uses a consistent EHR or IT system, request that any SSN be removed from the system, this should be done by the Chief Privacy Officer. They then will assign a patient identifier, (although your mileage will vary in terms of purging the SSN) since requirements for transparency of your own healthcare data are difficult to meet. The patient privacy officer can do this (within the managed system).
4. A national (NGO) approach using the c=US Health (X.500) based Informatics Directory that has been developed in conjunction with HHS, IHE, Hl7, state Health Information Exchanges.
5. Access to that Directory is (technically) possible using COTS via LDAP. 

A standard proven use case would be that of end to end encrypted S/MIME email with attached medical data between patient and provider.

This comes under the "Applicability Statement" of the Direct Project as the most secure email approach. Mail sent via TLS to a HISP via IMAPS or POP3S and subsequently converted to S/MIME at the HISP is not as secure, since the unencrypted data is exposed in the mail spool of the mail server and exposed to the root user, or a hacker.

TLS only encrypts to the end point. It prevents (assuming TLS 1.3) most MITM attacks and is approved by the IETF. Web server and client certificates are different forms of Key Usage. 

The same way that code signing is a different form of key usage. It goes to say (without much proof needed), that the relative difficulty to decrypt S/MIME email is higher to various threat actors is higher since each individual createst heir own keys. That data is then digitally signed and sent to a CA to create a certificate that has a trust value, from no trust of identity to a very high trust of identity, and thus a cost to match. A full blown "level 3 trust' in a PKI identity  is established by two forms of government ID, plus a notarized statement, mailed through the US mail. Level 4 trust is established by an in person visit to the CA, with the same information, plus biometrics. The specifics of this (and alternatives) are specified by NIST 800-63 for c=US. Additional data on the trust framework is available at the Federal PKI website, which primarily governs the policy for the CAs. For web based certificates, the best resource is the Mozilla Security Google Group, and the CA/Browser forum which covers the default CA certificates that are trusted by browsers, based on the CAB baseline requirements. 

Thus the number of keys is higher with millions of individual private keys. However this is a worthy discussion, since an average individual may not have adequate security, (without some guidance) to maintain the security of their private key, where a commercial entity is likely to use air gapped, offsite storage, in a HSM.

Medical organizations were paid millions of dollars to certify compliance with this capability under the portion of the Obama era stimulus act known as Meaningful Use 2.
Make sure you point out if that organization received funds for MU2 certification and does not subsequently provide this to you as a patient they are at risk for getting government funds for a service they do not provide. Note a patient portal that uses something other than S/MIME to send Direct email messages, (and there are other possible email systems that would not be compliant) and you should have a conversation with their vendor or IT staff.

In order to accomplish that, one can independently obtain a LOA 2 Digital Certificate from a valid Certificate Authority, and the recently passed 21st Century Cures act obligates your provider to exchange data with you, to send you your medical records, and to accept data you send them.

Once you have a client certificate, one also can do Mutual TLS, regardless of the S/MIME capability of the email client, although very few web servers are set up to accept mutual TLS. Mutual TLS is required in more specific security domains such as ATNA remote logging as an IHE profile that could be useful in keeping logs. especially in disaster situations, such as the recent Hurrican in Puerto Rico and Florida, where people in nursing homes died without adequate care. A log of transactions could form an evidentiary audit trail for legal discovery to deal with non-responsive institutions if you are responsible for the remote care of a family member.

Also in terms of elderly care, is the issue of requirements of DNR, and other contracts that express the will of the patient regarding their care via extra ordinary means, such as ventilation. A digital form statement can be created, later modified, and signed using a client signing certificate. Ideally, to meet c=US Federal Cross Certification certificate policy requirements, there should be two certificates, a signing certificate, and an encryption certificate.

Ben Laurie https://en.wikipedia.org/wiki/Ben_Laurie has suggested that there can be a tie in between user generated sovereign identity and the traditional PKI. The ability to fix or revoke a user generated ID, (which is possible via OCSP pushed out to browsers and most OS software libraries) may be relevant to user generated ID. For example, traditional systems are only slowly adapting to non-binary gender which may an element contributed by an attribute authority. See the "Tao Of Attributes" video discussion (fairly old) for more information.

The idea of this patient identity use case would be for patients to generate their own identifiers (probably using DKMS) and then memorialize or embed those identifiers in current legally "paved" mechanisms such as digital signatures which are cryptographically secure.

At the same time there are Block Chain applications as indidcated in the DKMS block diagrams.



