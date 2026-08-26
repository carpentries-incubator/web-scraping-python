---
title: "Ethics and Legality of Web Scraping"
teaching: 0 # teaching time in minutes
exercises: 0 # exercise time in minutes
---

:::::::::::::::::::::::::::::::::::::: questions 

- When is web scraping OK and when is it not?
- Is web scraping legal? Can I get into trouble?
- What are some ethical considerations to make?
- What can I do with the data that I’ve scraped?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

After completing this episode, participants should be able to...

- Discuss the legal and ethical implications of web scraping

::::::::::::::::::::::::::::::::::::::::::::::::

In this section we will look at some of the legal issues associated with web scraping. 

**Please note:**

  - **This does not constitute legal advice on the practice of web scraping.**
  - **This section is relevant to the UK. The law may be different in other countries - please seek relevant advice.**

## Copyright basics

Copyright is a form of intellectual property that automatically gives the creators or their employers certain rights over how their works can be used by others.  In the broadest sense, it allows creators to monetise their creations as well as to be identified as the creator. The Copyright, Design and Patents Act 1988 provide the legal protections for creators whilst also giving a number of exceptions that allow re-use without permission.

### Copyright coverage

Copyright covers a range of works, find a list of works covered by copyright below:

- Literary works (written works e.g. a book, computer code, websites)
- Dramatic works
- Musical works (e.g. a recording of a song)
- Databases
- Artistic works (e.g. a photo, painting, sculpture, diagram)
- Sound recordings
- Films (e.g. a recording of a moving image)
- Broadcasts (e.g. a transmission of a television programme)
- Typographical arrangements in a published edition

Not everything that a person creates is automatically granted protection by copyright. For example, the written sentence ‘Hello, how are you?’ is unlikely to be protected by copyright as it does not demonstrate creativity or originality and took the individual little effort or skill to write it.

### Duration of copyright

Copyright lasts for a longer period than most people expect:

- For most published items copyright lasts until the end of the 70th year in which the last creator of that work died
- The typographical arrangement of a publication (e.g. how a printed work has been laid out on the page and arranged) is in copyright for 25 years of the first edition that uses that typography.

It is important to note that the copyright duration in unpublished works (e.g. much archival material) may last for much longer than the 70 years after death of the creator.

The [UK Government website](https://www.gov.uk/government/publications/copyright-notice-duration-of-copyright-term/copyright-notice-duration-of-copyright-term) has a useful and detailed listing that covers the duration of copyright for a range of works.

### Copyright owner

Ownership determines control over the work’s use if not covered by a legal exception. Owners have the right to sell the work, license it to others, and object to its mistreatment. Unless overridden by a contract, copyright belongs to the person who created the work. It is crucial to contact the correct owner for permission to use a work, as ownership can change.  For example, an academic transfers copyright to a publisher as part of signing a publishing agreement or after a creator’s death it may transfer to their next of kin. Physical ownership of an item does not mean you also own the copyright in the item; these are two separate types of property ownership.

### Copyright exceptions

UK law provides a number of legal exceptions so that if you meet certain requirements, you can copy a work that is still in copyright without permission of the copyright owner.

## Scraping and copying

When scraping a website you are always copying content — even if only temporarily in memory. That means copyright law applies. A website’s text, images, code, and even its layout can be protected works.  Remember that if you want to copy any work still in copyright you will need a legal basis to allow that.  There is no ‘web scraping’ exception, the closest we have is an exception for non-commercial research of text and data analysis. 

A work that is no longer in copyright is called a Public Domain work; this means that its copyright duration has now passed and you are free to use the work without requiring permission.  Sometimes people will say that something is in the public domain believing that this means ‘publicly available.’  These are two separate things and just because something is publicly available for you to see online does not mean that it does not have copyright protection.  Most online items will still be in-copyright.  

### Non-commercial research text and data analysis

This exception allows you to copy items to bring together a corpus of materials for computational analysis if it meets the following criteria:

- You must have lawful access to the work (e.g. openly available online or via a library subscription. Bypassing a paywall is not lawful access); and
- It must be done for the sole purpose of non-commercial research; and
- Unless impossible the copy must be accompanied by sufficient acknowledgement.

If your use is covered by this exception any contract term that purports to restrict you from copying for this purpose is unenforceable. 

If you want to transfer the copy of the work to anyone else or use it for another purpose, then you would need permission of the copyright owner. This means that if you later wish to commercialise you may need to seek permissions. 

### Web scraping for commercial purposes

If your use were for a purpose other than non-commercial research then you have no legal exception to rely upon, you would need to abide by any contact terms.  Companies often do not want their website information to be scraped. To reduce your legal risk, you would need to ensure that you followed the website's own terms and conditions and check those as well as follow any restrictions mentioned in robot.txt files. Robot.txt files will tell web scraping tools which parts of the website it is not permitted to scape. The key points to consider are:

1.	Is there copyright in the material that you are scraping?
2.	Do you have legal access to the material?
3.	Would your use breach any contract you have with the provider (this could be the websites terms of service)? Remember that violating terms of a contract can constitute a breach of contract and risk legal claims against you. 
4.	Does your use go against any information in robot.txt files? 
5.	Are you trying to create a competing product or one that will economically harm the website that you are scraping? 
6.	Are there any data protection issues?

For commercial use it would be better to enter into an agreement with the people whose materials you are hoping to scrape. 

## Technical protection barriers

The Computer Misuse Act 1990 makes it a criminal offence to access data or a computer programme without authorisation.  This was aimed at preventing hacking attacks, but it does means that you should not circumvent any technical protection measures, logins, or CAPTCHA to scrape the service.  

## Database Rights

Database rights protect the substantial investment someone may have made to create their database in obtaining and verifying their data from independent sources.  Protection originally lasts for 15 years but can be longer if significant amendments are made to the database.  If you were to scrape substantial parts of their database (this can be quantity of material or the quality of it) then you may be infringing their rights especially if your use were to harm them economically e.g. by creating a competing product 

## Scraping of personal data within websites
If you do not require personal data as part of your research then try and ensure that your scraping does not collect the personal data of individuals e.g. names, email addresses etc.
As well as meeting copyright requirements you need to meet data protection requirements too.  In the UK, the fact that someone’s personal data may be publicly available does not mean that you can just re-use that information without either relying on an exception or exemption.  This includes information that you may find on social media websites or registers such as Companies House. If providing the people whose data you would be using with privacy information would be impossible or involve a disproportionate effort, then you must carry out a Data Protection Impact Assessment (DPIA).  Completing a DPIA helps you think about the risks involved in how you are using someone’s data, how you can mitigate them, and helps you assess if you have a legal basis for processing someone’s personal data.

## APIs
Where possible it may be better to use an authorised API for the webservice.  Several online services offer these as do some subscription databases provided by institutional libraries.  There is sometimes openly available information about this on provider websites.  Others require a library to provide the user with an API key and limit how many users can access this at one time.  Unfortunately, some providers require an additional cost for an API with their services.

## Denial of Service

The first and most important thing to be careful about when writing a web scraper is that it typically involves querying a website repeatedly and accessing a potentially large number of pages. For each of these pages, a request will be sent to the web server that is hosting the site, and the server will have to process the request and send a response back to the computer that is running our code. Each of these requests will consume resources on the server, during which it will not be doing something else, like for example responding to someone else trying to access the same site.

If we send too many such requests over a short span of time, we can prevent other "normal" users from accessing the site during that time or even cause the server to run out of resources and crash.

In fact, this is such an efficient way to disrupt a web site that hackers are often doing it on purpose. This is called a [Denial of Service (DoS) attack](https://en.wikipedia.org/wiki/Denial-of-service_attack).

Since DoS attacks are unfortunately a common occurrence on the Internet, modern web servers include measures to ward off such illegitimate use of their resources. They are watchful for large amounts of requests appearing to come from a single computer or IP address, and their first line of defence often involves refusing any further requests coming from this IP address.

A web scraper, even one with legitimate purposes and no intent to bring a website down, can exhibit similar behaviour and, if we are not careful, result in our computer being banned from accessing a website.

Scraping subscription resources provided by a library can also trigger systems to deny access.  It can be worth discussing use ahead of time with the relevant parties.

## Consider asking
Depending on the scope of your project, it might be worthwhile to consider asking the owners or curators of the data you are planning to scrape if they have it already available in a structured format that could suit your project. If your aim is to use their data for research, or to use it in a way that could potentially interest them, not only it could save you the trouble of writing a web scraper, but it could also help clarify straight away what you can and cannot do with the data.

## Further help

If you are affiliated with an institution or university, check with your institutional library or copyright office for further guidance on copyright, text and data mining, and licensing agreements. 


:::::::::::::::::::::::::::::::::: keypoints

- When web scraping you need to consider copyright, database rights, data protection and website terms.
- A UK exception allows non-commercial text and data mining only with lawful access and proper acknowledgement.
- Commercial scraping requires following terms of service, robots.txt.
- For all web scraping you need to avoid any circumvention of technical barriers.
- Key risks include collecting personal data, overwhelming servers, and inadvertently infringing rights — using APIs or asking data owners is often safer.

::::::::::::::::::::::::::::::::::::::::::::
