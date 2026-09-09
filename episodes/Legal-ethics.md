---
title: "Ethics and Legality of Web Scraping"
teaching: 0 # teaching time in minutes
exercises: 0 # exercise time in minutes
---

:::::::::::::::::::::::::::::::::::::: questions 

- When is web scraping OK and when is it not?
- Is web scraping legal? Can I get into trouble?
- What are some ethical considerations to make?
- What can I do with the data that I've scraped?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

After completing this episode, participants should be able to...

- Discuss the legal and ethical implications of web scraping

::::::::::::::::::::::::::::::::::::::::::::::::

In this section we will look at some of the legal and ethical issues associated with web scraping. 

**Please note:**

  - **This does not constitute legal advice on the practice of web scraping.**
  - **The law differs between countries. Country-specific sections are provided below for guidance — please seek relevant legal advice for your jurisdiction.**

## Copyright basics

Copyright is a form of intellectual property that automatically gives the creators or their employers certain rights over how their works can be used by others. In the broadest sense, it allows creators to monetise their creations as well as to be identified as the creator. Most countries have copyright legislation that provides legal protections for creators whilst also giving a number of exceptions that allow re-use without permission.

### Copyright coverage

Copyright covers a range of works, find a list of works commonly covered by copyright below:

- Literary works (written works e.g. a book, computer code, websites)
- Dramatic works
- Musical works (e.g. a recording of a song)
- Databases
- Artistic works (e.g. a photo, painting, sculpture, diagram)
- Sound recordings
- Films (e.g. a recording of a moving image)
- Broadcasts (e.g. a transmission of a television programme)
- Typographical arrangements in a published edition

Not everything that a person creates is automatically granted protection by copyright. For example, the written sentence 'Hello, how are you?' is unlikely to be protected by copyright as it does not demonstrate creativity or originality and took the individual little effort or skill to write it.

### Duration of copyright

Copyright lasts for a longer period than most people expect. The exact duration varies by country and by the type of work, but in many jurisdictions copyright in literary, dramatic, musical, and artistic works lasts for the life of the creator plus a set number of decades (commonly 50 to 70 years after the creator's death).

It is important to note that the copyright duration in unpublished works (e.g. much archival material) may last for much longer.

:::::::::::::::::::::::::::::::::::::::::: spoiler

### UK: Duration of Copyright

- For most published items copyright lasts until the end of the 70th year in which the last creator of that work died.
- The typographical arrangement of a publication (e.g. how a printed work has been laid out on the page and arranged) is in copyright for 25 years of the first edition that uses that typography.

The [UK Government website](https://www.gov.uk/government/publications/copyright-notice-duration-of-copyright-term/copyright-notice-duration-of-copyright-term) has a useful and detailed listing that covers the duration of copyright for a range of works.

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::::: spoiler

### US: Duration of Copyright

- For works created on or after January 1, 1978, copyright lasts for the life of the author plus 70 years.
- For works made for hire, anonymous works, or pseudonymous works, copyright lasts 95 years from first publication or 120 years from creation, whichever is shorter.
- The cutoff date for works entering the public domain advances each year. For example, in the year 2026 the 70 year rule established that works published before 1931 are in the public domain (specifically, works published in the United States before January 1, 1931 have entered the public domain because their copyright terms have expired).

The [US Copyright Office](https://www.copyright.gov/what-is-copyright/) provides detailed information about copyright basics and the duration of copyright.

::::::::::::::::::::::::::::::::::::::::::::::::::

### Copyright owner

Ownership determines control over the work's use if not covered by a legal exception. Owners have the right to sell the work, license it to others, and object to its mistreatment. Unless overridden by a contract, copyright belongs to the person who created the work. It is crucial to contact the correct owner for permission to use a work, as ownership can change. For example, an academic transfers copyright to a publisher as part of signing a publishing agreement or after a creator's death it may transfer to their next of kin. Physical ownership of an item does not mean you also own the copyright in the item; these are two separate types of property ownership.

### Copyright exceptions

Most countries provide legal exceptions so that if you meet certain requirements, you can copy a work that is still in copyright without permission of the copyright owner. However, the scope and nature of these exceptions vary significantly between jurisdictions.

:::::::::::::::::::::::::::::::::::::::::: spoiler

### UK: Copyright Exceptions

UK law (the Copyright, Designs and Patents Act 1988) provides a number of legal exceptions. One key exception relevant to web scraping is the exception for non-commercial research of text and data analysis (see below).

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::::: spoiler

### US: Copyright Exceptions (Fair Use)

In the United States, the primary copyright exception is the doctrine of **Fair Use** (17 USC Section 107). Fair Use is evaluated on a case-by-case basis using four factors:

1. The purpose and character of the use (e.g. commercial vs. non-profit educational, and whether it is "transformative")
2. The nature of the copyrighted work
3. The amount and substantiality of the portion used in relation to the whole
4. The effect of the use upon the potential market for or value of the copyrighted work

Courts have found copying and indexing of web content to be fair use in some cases (e.g. *Authors Guild v. Google*), particularly when the use is transformative. Commercial use can make relying on fair use more challenging, but does not automatically preclude it, as all four factors are weighed together. However, fair use is fact-specific and there is no guarantee that any particular scraping activity will qualify.

::::::::::::::::::::::::::::::::::::::::::::::::::

## Scraping and copying

When scraping a website you are always copying content — even if only temporarily in memory. That means copyright law applies. A website's text, images, code, and even its layout can be protected works. Remember that if you want to copy any work still in copyright you will need a legal basis to allow that. There is no universal 'web scraping' exception in copyright law.

A work that is no longer in copyright is called a Public Domain work; this means that its copyright duration has now passed and you are free to use the work without requiring permission. Sometimes people will say that something is in the public domain believing that this means 'publicly available.' These are two separate things and just because something is publicly available for you to see online does not mean that it does not have copyright protection. Most online items will still be in-copyright.

:::::::::::::::::::::::::::::::::::::::::: spoiler

### UK: Non-commercial Research Text and Data Analysis Exception

The UK provides a specific exception that allows you to copy items to bring together a corpus of materials for computational analysis if it meets the following criteria:

- You must have lawful access to the work (e.g. openly available online or via a library subscription. Bypassing a paywall is not lawful access); and
- It must be done for the sole purpose of non-commercial research; and
- Unless impossible the copy must be accompanied by sufficient acknowledgement.

If your use is covered by this exception any contract term that purports to restrict you from copying for this purpose is unenforceable. 

If you want to transfer the copy of the work to anyone else or use it for another purpose, then you would need permission of the copyright owner. This means that if you later wish to commercialise you may need to seek permissions.

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::::: spoiler

### US: Fair Use and Text/Data Mining

In the US, text and data mining for research purposes may qualify as fair use, particularly if the use is transformative (i.e. you are extracting facts or generating new insights rather than republishing the original expression). Court decisions have supported this interpretation:

- *Authors Guild v. Google* (2015): Google's digitisation of books to create a searchable index and display snippets was held to be fair use because it was highly transformative and did not substitute for the original works.

However, there is no specific statutory text and data mining exception in US copyright law. Each case depends on its specific facts, and commercial uses face greater scrutiny.

::::::::::::::::::::::::::::::::::::::::::::::::::

### Web scraping for commercial purposes

If your use is for a commercial purpose then you are less likely to be able to rely on legal exceptions. To reduce your legal risk, you should consider the following:

1. Is there copyright in the material that you are scraping?
2. Do you have legal access to the material?
3. Would your use breach any contract you have with the provider (this could be the website's terms of service)? Remember that violating terms of a contract can constitute a breach of contract and risk legal claims against you.
4. Does your use go against any information in robots.txt files?
5. Are you trying to create a competing product or one that will economically harm the website that you are scraping?
6. Are there any data protection issues?

For commercial use it would be better to enter into an agreement with the people whose materials you are hoping to scrape.

## Technical protection barriers

Circumventing technical protection measures to access data for scraping can carry criminal or civil penalties in most jurisdictions. You should not circumvent any technical protection measures, logins, or CAPTCHA to scrape a service.

:::::::::::::::::::::::::::::::::::::::::: spoiler

### UK: Computer Misuse Act 1990

The Computer Misuse Act 1990 makes it a criminal offence to access data or a computer programme without authorisation. This was aimed at preventing hacking attacks, but it does mean that you should not circumvent any technical protection measures, logins, or CAPTCHA to scrape a service.

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::::: spoiler

### US: Computer Fraud and Abuse Act (CFAA)

The Computer Fraud and Abuse Act (18 USC 1030) makes it illegal to access a computer "without authorization" or in a way that "exceeds authorized access." 

Two key court decisions have shaped how the CFAA applies to web scraping:

- *Van Buren v. United States* (2021): The Supreme Court narrowed the interpretation of "exceeds authorized access," holding that it applies to accessing files or databases that an individual is not entitled to access, rather than using authorized access for an improper purpose or in violation of terms of service.
- *HiQ Labs v. LinkedIn* (2022): On remand following *Van Buren*, the Ninth Circuit reaffirmed that scraping publicly available data on the open web—where no password or authentication gate exists—generally does not constitute access "without authorization" under the CFAA. 

However, *HiQ* did not make all web scraping legal: scraping behind login barriers, bypassing CAPTCHAs or technical access controls, or ignoring formal cease-and-desist revocations can still trigger liability under the CFAA or state breach-of-contract and common-law doctrines.

::::::::::::::::::::::::::::::::::::::::::::::::::

## Database Rights

Some jurisdictions provide a separate "database right" that protects the substantial investment someone may have made to create their database in obtaining and verifying data from independent sources.

:::::::::::::::::::::::::::::::::::::::::: spoiler

### UK: Database Rights (Sui Generis)

Database rights in the UK (derived from EU law) protect the substantial investment someone may have made to create their database in obtaining and verifying their data from independent sources. Protection originally lasts for 15 years but can be longer if significant amendments are made to the database. If you were to scrape substantial parts of their database (this can be quantity of material or the quality of it) then you may be infringing their rights especially if your use were to harm them economically e.g. by creating a competing product.

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::::: spoiler

### US: No Sui Generis Database Right

The United States does not have a sui generis database right like the UK/EU. However, databases may still be protected under copyright if the selection, coordination, or arrangement of the data is sufficiently creative (*Feist Publications v. Rural Telephone Service*, 1991). Purely factual compilations arranged in an obvious way (e.g. alphabetical phone listings) are not protected. Additionally, some databases may be protected through contract law (Terms of Service) or trade secret law.

::::::::::::::::::::::::::::::::::::::::::::::::::

## Scraping of personal data within websites

If you do not require personal data as part of your research then try and ensure that your scraping does not collect the personal data of individuals e.g. names, email addresses etc.

As well as meeting copyright requirements you need to meet data protection requirements too. In most jurisdictions, the fact that someone's personal data may be publicly available does not mean that you can just re-use that information without legal basis. This includes information that you may find on social media websites or public registers.

:::::::::::::::::::::::::::::::::::::::::: spoiler

### UK: Data Protection (UK GDPR)

In the UK, the fact that someone's personal data may be publicly available does not mean that you can just re-use that information without either relying on an exception or exemption. This includes information that you may find on social media websites or registers such as Companies House. If providing the people whose data you would be using with privacy information would be impossible or involve a disproportionate effort, then you must carry out a Data Protection Impact Assessment (DPIA). Completing a DPIA helps you think about the risks involved in how you are using someone's data, how you can mitigate them, and helps you assess if you have a legal basis for processing someone's personal data.

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::::: spoiler

### US: Data Privacy

The United States does not have a single comprehensive federal data protection law equivalent to the UK GDPR. Instead, data privacy is governed by a patchwork of federal and state laws:

- **State laws**: California's CCPA/CPRA, Virginia's VCDPA, Colorado's CPA, and others provide varying levels of consumer data protection. Importantly, unlike the UK/EU GDPR, many US state statutes explicitly exclude publicly available information (such as data lawfully made available from government records or widely distributed media) from their definition of personal data.
- **Sectoral federal laws**: HIPAA (health data), FERPA (education records), COPPA (children's data), and others apply in specific contexts.
- **FTC Act**: The Federal Trade Commission can take action against unfair or deceptive practices involving personal data.

When scraping data that includes personal information of US residents, be mindful of applicable state privacy laws and any sectoral federal regulations that may govern the specific type of data collected.

::::::::::::::::::::::::::::::::::::::::::::::::::

## APIs
Where possible it may be better to use an authorised API for the web service. Several online services offer these as do some subscription databases provided by institutional libraries. There is sometimes openly available information about this on provider websites. Others require a library to provide the user with an API key and limit how many users can access this at one time. Unfortunately, some providers require an additional cost for an API with their services.

## Denial of Service

The first and most important thing to be careful about when writing a web scraper is that it typically involves querying a website repeatedly and accessing a potentially large number of pages. For each of these pages, a request will be sent to the web server that is hosting the site, and the server will have to process the request and send a response back to the computer that is running our code. Each of these requests will consume resources on the server, during which it will not be doing something else, like for example responding to someone else trying to access the same site.

If we send too many such requests over a short span of time, we can prevent other "normal" users from accessing the site during that time or even cause the server to run out of resources and crash.

In fact, this is such an efficient way to disrupt a web site that hackers are often doing it on purpose. This is called a [Denial of Service (DoS) attack](https://en.wikipedia.org/wiki/Denial-of-service_attack).

Since DoS attacks are unfortunately a common occurrence on the Internet, modern web servers include measures to ward off such illegitimate use of their resources. They are watchful for large amounts of requests appearing to come from a single computer or IP address, and their first line of defence often involves refusing any further requests coming from this IP address.

A web scraper, even one with legitimate purposes and no intent to bring a website down, can exhibit similar behaviour and, if we are not careful, result in our computer being banned from accessing a website.

Scraping subscription resources provided by a library can also trigger systems to deny access. It can be worth discussing use ahead of time with the relevant parties.

## Consider asking
Depending on the scope of your project, it might be worthwhile to consider asking the owners or curators of the data you are planning to scrape if they have it already available in a structured format that could suit your project. If your aim is to use their data for research, or to use it in a way that could potentially interest them, not only it could save you the trouble of writing a web scraper, but it could also help clarify straight away what you can and cannot do with the data.

## Further help

If you are affiliated with an institution or university, check with your institutional library or copyright office for further guidance on copyright, text and data mining, and licensing agreements. 


:::::::::::::::::::::::::::::::::::::: keypoints

- When web scraping you need to consider copyright, database rights, data protection and website terms.
- Copyright exceptions vary by country: the UK has a specific text and data mining exception for non-commercial research; the US relies on fair use doctrine.
- Commercial scraping requires following terms of service and robots.txt.
- For all web scraping you need to avoid any circumvention of technical barriers.
- Key risks include collecting personal data, overwhelming servers, and inadvertently infringing rights — using APIs or asking data owners is often safer.

::::::::::::::::::::::::::::::::::::::::::::::::
