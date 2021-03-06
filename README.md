# etholos1
This is an initial commit for the X.509v3/X.500 c=US Healthcare identity and informatics Directory. 

While the "Directory" and related PKI is well established, it is a critical (if not entirely well understood) part of network infrastructure due to the technical complexity. All members of the X.500 Directory are unique, where in separate databases and disconnected directories, uniqueness is not guaranteed. This is where probabilistic algorithm matching enters the picture.

Thus one needs to ask, at what level is my specific entry unique? This might be the entire Internet for self generated identity on a block chain, unique within a hosptital healthcare system, unique within an electronic healthcare system, or unique within an organization like CMS or the VA or within a specific State. 


As a result several PKI based associations have developed best practices that surround the use of the PKI, which may or may not involve IETF standards. 

Since the IETF opposes "pervasive monitoring" of data, certain threat mitigations exist for various actors that may attempt to abuse your healthcare data. If you had behavioral data as part of a standard form 86 security clearance, that mentioned treatment for alcoholism, this confidential data has already been part of a breach of data by OMB.

https://www.wired.com/2015/06/opm-breach-security-privacy-debacle/

These threat actors range from an insider employee, up to and including state actors. 

A separate ***policy matrix specification*** will make clear the requirements of Health Care providers to accept and securely store, and share your health care data with other covered entities when using the c=US relying party agreement and trust framework.

While the PKI has been extensively tested, and documented in security realms; this particular repository use case will focus on generating soverign patient identity using experimental protocols funded by recent research at Department of Homeland Security to develop "sovereign identity" with DKMS. This in turn will be linked to a Country rooted X.500 Directory service which has been tested previously with a Healthcare Standards and Interoperability schema, of which the model is currently being developed under a HL7 ballot with futher data elements, than the original IHE version which was adopted to X.500 by ISODE.

The standard on which to start off is this. https://www.iso.org/standard/51432.html What is important about this standard, and what is subsequently unique to the US, is the fact that both patients and providers are connected in the ISO version, where in the US the Federal Government has been prohibited by Congress from funding patient identifiers. That is a separate and well documented thread in terms of risks, how much money would be saved with a complete system, and the amount patient errors reduced.

At one point CHIME offered a 1 Million dollar HeroX prize for a development solution, and some two years later, (after a great deal of development and publicity noise), essentially decided it was too difficult to do on their own.



Of course they set up poor requirements, which almost guaranteed this result, (at least that's what I told them).

So CHIME played a part in both advancing and delaying Patient ID. 

https://www.hospitalemrandehr.com/2017/11/17/chime-suspends-the-1-million-dollar-national-patient-id-challenge/


The point is to augment the quality and depth of the current PKI under c=US, or country equals US, for which I have been a private manager and developer since the 1990s. There are a number of related efforts which I will list here to improve the PKI for the end user. 

Saving costs by adopting a National Patient Identifier

The HIPAA legislation described and  encouraged a NPI, but after the legislation was passed, it appeared that a centralized database would be likely be hacked. As such Congress decided to pass legislation that (still currently) forbids HHS from funding an NPI. 

Using SSN for a NPI substitute, or patient matching algorithms has been similarly problematic. So (uniquely), here in the US, there are few options.

1. An internal government solution of patient identity (established recently by CMS) to mitigate Identity Theft for seniors. 
2. An ASTM/ANSI standard for Patient ID, written by Barry Hieb, and implemented by his company which issues Public and Private Patient Identifiers https://www.gpii.info/
3. As a patient of a hosptital or care organization that uses a consistent EHR or IT system, request that any SSN be removed from the system, this should be done by the Chief Privacy Officer. They then will assign a patient identifier, (although your mileage will vary in terms of purging the SSN) since requirements for transparency of your own healthcare data are difficult to meet. The patient privacy officer can do this (within the managed system).
4. A national (NGO) approach using the c=US Health (X.500) based Informatics Directory that has been developed in conjunction with HHS, IHE, Hl7, state Health Information Exchanges.
5. Access to that Directory is (technically) possible using COTS via LDAP. 

A standard proven use case would be that of end to end encrypted S/MIME email with attached medical data between patient and provider.

This comes under the "Applicability Statement" of the Direct Project as the most secure email approach. Mail sent via TLS to a HISP via IMAPS or POP3S and subsequently converted to S/MIME at the HISP is not as secure, since the unencrypted data is exposed in the mail spool of the mail server and exposed to the root user, or a hacker. Hacking softwate can be very sophisicated and only exist in the memory (not software) of a device. 

TLS only encrypts to the end point. It prevents (assuming TLS 1.3) most MITM attacks and is approved by the IETF. Web server and client certificates are different forms of Key Usage. 

The same way that code signing is a different form of key usage. It goes to say (without much proof needed), that the relative difficulty to decrypt S/MIME email is higher to various threat actors is higher since each individual createst heir own keys. That data is then digitally signed and sent to a CA to create a certificate that has a trust value, from no trust of identity to a very high trust of identity, and thus a cost to match.

A full blown "level 3 trust' in a PKI identity  is established by two forms of government ID, plus a notarized statement, mailed through the US mail. Level 4 trust is established by an in person visit to the CA, with the same information, plus biometrics. 

The specifics of this (and alternatives) are specified by NIST 800-63 for c=US. This level of assurance is appropriate to repesent your identity to "relying parties". As was said at a HIPAA seminar at NIST, it's good enough for nukes, it should be good enough for healthcare.

Additional data on the trust framework is available at the Federal PKI website, which primarily governs the policy for the CAs. For web based certificates, the best resource is the Mozilla Security Google Group, and the CA/Browser forum which covers the default CA certificates that are trusted by browsers, based on the CAB baseline requirements. 

Thus the number of keys is higher with millions of individual private keys. However this is a worthy discussion, since an average individual may not have adequate security, (without some guidance) to maintain the security of their private key, where a commercial entity is likely to use air gapped, offsite storage, in a HSM.

Medical organizations were paid millions of dollars to certify compliance with this capability under the portion of the Obama era stimulus act known as Meaningful Use 2.
Make sure you point out if that organization received funds for MU2 certification and does not subsequently provide this to you as a patient they are at risk for getting government funds for a service they do not provide. Note a patient portal that uses something other than S/MIME to send Direct email messages, (and there are other possible email systems that would not be compliant) and you should have a conversation with their vendor or IT staff.

In order to accomplish that, one can independently obtain a LOA 2 Digital Certificate from a valid Certificate Authority, and the recently passed 21st Century Cures act obligates your provider to exchange data with you, to send you your medical records, and to accept data you send them.

Once you have a client certificate, one also can do Mutual TLS, regardless of the S/MIME capability of the email client, although very few web servers are set up to accept mutual TLS. Mutual TLS is required in more specific security domains such as ATNA remote logging as an IHE profile that could be useful in keeping logs. especially in disaster situations, such as the recent Hurrican in Puerto Rico and Florida, where people in nursing homes died without adequate care. A log of transactions could form an evidentiary audit trail for legal discovery to deal with non-responsive institutions if you are responsible for the remote care of a family member.

Also in terms of elderly care, is the issue of requirements of DNR, and other contracts that express the will of the patient regarding their care via extra ordinary means, such as ventilation. A digital form statement can be created, later modified, and signed using a client signing certificate. Ideally, to meet c=US Federal Cross Certification certificate policy requirements, there should be two certificates, a signing certificate, and an encryption certificate.

Ben Laurie https://en.wikipedia.org/wiki/Ben_Laurie has suggested that there can be a tie in between user generated sovereign identity and the traditional PKI. The ability to fix or revoke a user generated ID, (which is possible via OCSP pushed out to browsers and most OS software libraries) may be relevant to user generated ID. For example, traditional systems are only slowly adapting to non-binary gender which may an element contributed by an attribute authority. See the "Tao Of Attributes" video discussion (fairly old) for more information.

The idea of this patient identity use case would be for patients to generate their own identifiers (probably using DKMS) and then memorialize or embed those identifiers in current legally "paved" mechanisms such as digital signatures which are cryptographically secure.

At the same time there are Block Chain applications as indidcated in the DKMS block diagrams.


Notes:

Contrast between Patient Matching and Patient Identity circa 2014 by Peel This essentially makes the case for self generated identity that can be networked across the healthcare system. 

Peel D.C. “Patient Identification and Matching Initial Findings.” Patient Privacy Rights. December 16, 2013. Available at http://patientprivacyrights.org/wp-content/uploads/2013/12/PPR-Patient-Matching-Testimony-for-12.16.13.pdf.




