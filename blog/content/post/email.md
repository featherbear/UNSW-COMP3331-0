---
title: "Emails"
date: 2019-10-01T09:00:00+10:00

description: "Ding! You've got mail!"
hiddenFromHomePage: false
postMetaInFooter: false

flowchartDiagrams:
  enable: false
  options: ""

sequenceDiagrams:
  enable: false
  options: ""
---

[smtp]: #simple-mail-transfer-protocol-smtp
[pop]: #post-office-protocol-pop
[imap]: #internet-mail-access-protocol-imap
[mta]: #mail-transport-agent-mta
[mua]: #mail-user-agent-mua
[mda]: #mail-delivery-agent-mda

> **TLDR**  
> Your [mail client](#mail-user-agent-mua) contacts your [email server](#mail-transport-agent-mta) over [SMTP].  
> Your [email server](#mail-transport-agent-mta) contacts their [email server](#mail-transport-agent-mta) over [SMTP].  
> Their [email server](#mail-transport-agent-mta) then [stores the message](#mail-delivery-agent-mda).  
> Their [email client](#mail-user-agent-mua) retrieves the email over either [POP] or [IMAP].

> ![](https://upload.wikimedia.org/wikipedia/commons/a/af/Schema_of_e-mail_delivery.png)

# Email

The email system composes of, a lot of acronyms.

- [Mail User Agent (MUA)](#mail-user-agent-mua)
- [Mail Transport Agent (MTA)](#mail-transport-agent-mta)
  - Mail Submission Agent (MSA)
  - Mail Retrieval Agent (MRA)
- [Mail Delivery Agent (MDA)](#mail-delivery-agent-mda)
- Protocols
  - [Simple Mail Transport Protocol (SMTP)](#simple-mail-transfer-protocol-smtp)
  - [Post Office Protocol (POP)](#post-office-protocol-pop)
  - [Internet Mail Access Protocol (IMAP)](#internet-mail-access-protocol-imap)

_Note: A **mail server** is a machine which embeds a mailbox, an [MTA] and an [MDA], plus the respective server software for [SMTP], [POP] and [IMAP]_

## Mail User Agent (MUA)

The **MUA** is your email client, where you compose, send and receive emails.

Your MUA is responsible for fetching your mailbox (either through [IMAP] or [POP]) to retrieve emails.  
To send emails, your MUA contacts your [MTA] (Mail Transport Agent) via [SMTP].

# Mail Transport Agent (MTA)

The **MTA** is a software that handles the delivery of your email to the recipient's MTA.

Your [MUA] (Mail User Agent) first contacts your local MTA over the [SMTP] (Simple Mail Transport Protocol) protocol.  
Your MTA then contacts the recipient's [MTA], where the mail is then passed onto their [MDA] (Mail Delivery Agent).

This software is responsible for (trying to) sending/receiving emails even when your/their computer is offline.

# Mail Delivery Agent (MDA)

The **MDA** handles the reception of emails, where they are sorted and placed into a local mailbox.

When your [MUA] (Mail User Agent) wants a copy of the emails, it will contact either a [POP] (Post Office Protocol) Server, or an [IMAP] (Internet Mail Access Protocol) Server. These servers are responsible for accessing the local mailbox.

# Protocols

## Simple Mail Transfer Protocol (SMTP)

The **SMTP** protocol is used to **SEND** emails, rather than to receive

- RFC5321
- Persistent connection (Connection remains open until closed)
- 7-bit ASCII
- `\r\n.\r\n` to signify the end of message

## Post Office Protocol (POP)

The **POP** protocol is used to **RECEIVE** emails, rather than to send

- RFC1939
- One way synchronisation (does not update the "read" property of an email)

## Internal Mail Access Protocol (IMAP)

The **IMAP** protocol is used to **RECEIVE** emails, rather than to send

- RFC1730
- Two way synchronisation (can mark opened emails as "read")
- Better than [POP]

---

> Why do we have the sender's mail server

In the case that the receiver's mail server is down, the sender's mail server will handle the delivery of the message.  
In this way, the sender's computer can be turned off / disconnected.

(Ahem, timezones!)

---

# Phishing

- Spear Phishing
- Clone Phishing
