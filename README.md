# Task-2-Analyze-a-Phishing-Email-Sample.
**
#Sample Phishing Email**

Subject: Urgent: Your Account Will Be Locked in 24 Hours
From: "PayPal Security Team" <support@secure-paypa1.com>
To: you@example.com
Date: June 23, 2025
Body:

    Dear Customer,

    We noticed suspicious activity on your PayPal account.
    For your protection, we will limit access unless you verify your identity.

    Click the link below to verify your account:
    https://paypal.com.verify.account.security-check.com

    Failure to act in the next 24 hours will result in permanent suspension of your account.

    Sincerely,
    PayPal Security Team

**# Summary of Phishing Traits Found**
1. Spoofed sender address: support@secure-paypa1.com (mimics PayPal)
2. Failed email authentication: SPF, DKIM/DMARC checks failed
3. Malicious URL: Link redirects to a phishing site using a fake PayPal subdomain
4. Urgency in message: Threats of account lock within 24 hours
5. Generic greeting: "Dear Customer" instead of user's actual name
6. No branding/logo: Missing standard PayPal branding and contact information

#Used Online Header Analyzers (Google’s Message Header Analyzer)
1. Access the Email: Open the email you want to analyze in your email client (Gmail)
2. Locate the Email Header:
    Open the email.
    Click on the three vertical dots (More options) in the top right corner of the email.
    Select "Show original." This will open a new tab with the full email header and the original message.
3. Analyse email header: Once you have the email header, you will see a lot of technical information. Key components to look for are:
     Check the "From" field to see the sender's email address.
     Return-Path
     Received
     SPF (Sender Policy Framework): Look for lines indicating SPF results. If it says "fail," it means the email was not sent from an authorized server.
     DKIM (DomainKeys Identified Mail): Check for DKIM signatures. If it says "pass," the email is likely legitimate. If it says "fail," it may be spoofed.
     DMARC (Domain-based Message Authentication, Reporting & Conformance): Look for DMARC results. A "pass" indicates that the email aligns with the sender's domain policies.
4. Use Online Header Analyzers


**# Sample email header used to analyse **
Delivered-To: you@example.com
Received: by 2002:a17:906:dc82:0:0:0:0 with SMTP id d2csp389394ejb;
        Mon, 24 Jun 2025 10:16:35 -0700 (PDT)
X-Received: by 2002:a05:6e02:240b:b0:1a7:96ea:4e10 with SMTP id s11-20020a056e02240b00b01a796ea4e10mr24023931pfg.23.1687625795667;
        Mon, 24 Jun 2025 10:16:35 -0700 (PDT)
Return-Path: <support@secure-paypa1.com>
Received: from mail.secure-paypa1.com (mail.secure-paypa1.com. [185.234.65.12])
        by mx.google.com with ESMTPS id y9si25126511plk.12.2025.06.24.10.16.35
        for <you@example.com>
        (version=TLS1_3 cipher=TLS_AES_256_GCM_SHA384 bits=256/256);
        Mon, 24 Jun 2025 10:16:35 -0700 (PDT)
Received-SPF: fail (google.com: domain of support@secure-paypa1.com does not designate 185.234.65.12 as permitted sender) client-ip=185.234.65.12;
Authentication-Results: mx.google.com;
       spf=fail (google.com: domain of support@secure-paypa1.com does not designate 185.234.65.12 as permitted sender) smtp.mailfrom=support@secure-paypa1.com;
       dkim=none (message not signed);
       dmarc=fail (p=REJECT sp=REJECT dis=NONE) header.from=secure-paypa1.com
From: "PayPal Security Team" <support@secure-paypa1.com>
To: you@example.com
Subject: Urgent: Your Account Will Be Locked in 24 Hours
Date: Mon, 24 Jun 2025 13:16:25 -0400
Message-ID: <149b35a21c244a9e9e3b3f6ddc@secure-paypa1.com>
Content-Type: text/html; charset=UTF-8
Content-Transfer-Encoding: quoted-printable
MIME-Version: 1.0

HEADER RESULTS SHARED AS SCREENSHOT 
