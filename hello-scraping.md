---
title: "Hello-Scraping"
teaching: 40
exercises: 10
---

:::::::::::::::::::::::::::::::::::::: questions 

- What’s behind a website, and how can I extract information from it?
- What ethical and legal considerations should I keep in mind before scraping a website?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Identify the structure and key components of an HTML document.
- Use BeautifulSoup to locate elements, tags, attributes, and text within an HTML page.
- Recognize situations where web scraping is inappropriate or not permitted for accessing data.

::::::::::::::::::::::::::::::::::::::::::::::::

## Introduction

This workshop is a continuation of our Introduction to Web Scraping workshop.
If you're looking for a gentler introduction that uses XPath and the Scraper Chrome extension, take a look at the [workshop materials for that workshop](https://carpentries-incubator.github.io/lc-webscraping/).

Here, we’ll revisit some of those core ideas to build a more hands-on understanding of how content and data are structured on the web. 
We’ll start by exploring what HTML (Hypertext Markup Language) is and how it uses tags to organize and format content.
Then, we’ll introduce the BeautifulSoup library to parse HTML and make it easier to search for and extract specific elements from a webpage.

We'll begin with simple examples and gradually move on to scraping more complex, real-world websites.

## HTML quick overview

All websites have a Hypertext Markup Language (HTML) document behind them.
Below is an example of HTML for a very simple webpage that contains just three sentences.
As you look through it, try to imagine how the website would appear in a browser.

```html
<!DOCTYPE html>
<html>
<head>
<title>Sample web page</title>
</head>
<body>
<h1>h1 Header #1</h1>
<p>This is a paragraph tag</p>
<h2>h2 Sub-header</h2>
<p>A new paragraph, now in the <b>sub-header</b></p>
<h1>h1 Header #2</h1>
<p>
This other paragraph has two hyperlinks,
one to <a href="https://carpentries.org/">The Carpentries homepage</a>,
and another to the
<a href="https://carpentries.org/workshops/past-workshops/">past workshops</a> page.
</p>
</body>
</html>
```

If you save that text in a file with a .html extension —using a simple text editor like Notepad on Windows or TextEdit on macOS— and open it in your web browser, the browser will interpret the markup language and display a nicely formatted web page.

![](fig/simple_website.PNG){alt="Screenshot of a simple website with the previews HTML"}

When you open an HTML file in your browser, what it's really doing is reading a structured document made up of **elements**, each marked by **tags** inside angle brackets (< and >).
For instance, the HTML root element, which delimits the beginning and end of an HTML document, is identified by the `<html>` tag.

Most elements have both an opening tag and a closing tag, which define the start and end of that element.
For example, in the simple website we looked at earlier, the head element begins with `<head>` and ends with `</head>`.

Because elements can be nested inside one another, an HTML document forms a tree structure, where each element is a node that can contain child nodes, as illustrated in the image below.

![The Document Object Model (DOM) that represents an HTML document with a tree structure. Source: Wikipedia. Author: Birger Eriksson](https://upload.wikimedia.org/wikipedia/commons/5/5a/DOM-model.svg){alt="Screenshot of a simple website with the previews HTML"}

Finally, we can define or modify the behavior, appearance, or functionality of an element using **attributes**.
Attributes appear inside the opening tag and consist of a name and a value, formatted like `name="value"`.

For example, in the simple website, we added a hyperlink using the `<a>...</a>` tags.
To specify the destination URL, we used the `href` attribute inside the opening `<a>` tag like this: `<a href="https://carpentries.org/workshops/past-workshops/">past workshops</a>`.

Here is a non-exhaustive list of common HTML elements and their purposes:

- `<hmtl>...</html>`: The root element that contains the entire document.
- `<head>...</head>`: Contains metadata such as the page title that the browser displays.
- `<body>...</body>`: Contains the content that will be shown on the webpage.
- `<h1>...</h1>, <h2>...</h2>, <h3>...</h3>`: Define headers of levels 1, 2, 3, and so on.
- `<p>...</p>`: Represents a paragraph.
- `<a href="">...</a>`: Creates a hyperlink; the destination URL is set with the href attribute.
- `<img src="" alt="">`: Embeds an image, with the image source specified by `src` and alternative text provided by `alt`. It doesn't have an opening tag.
- `<table>...</table>, <th>...</th>, <tr>...</tr>, <td>...</td>`: Define a table structure, with headers (`<th>`), rows (`<tr>`), and cells (`<td>`).
- `<div>...</div>`: Groups sections of HTML content together.
- `<script>...</script>`: Embeds or links to JavaScript code.

In the list above, we mentioned some attributes specific to hyperlink (`<a>`) and image (`<img>`) elements, but there are also several global attributes that most HTML elements can have.
These are especially useful for identifying elements when web scraping:

- `id=""`: Assigns a unique identifier to an element; this ID must be unique within the entire HTML document. 
- `title=""`: Provides extra information about the element, shown as a tooltip when the user hovers over it.
- `class=""`: Applies a common styling or grouping to multiple elements at once.

To summarize: **elements** are identified by **tags**, and **attributes** let us assign properties or identifiers to those elements.
Understanding this structure will make it much easier to extract specific data from a website.

## Parsing HTML with BeautifulSoup

Now that we understand how a website is structured, we can begin extracting information from it.
The `BeautifulSoup` package is our main tool for this task —it parses the HTML so we can programmatically search for and access the elements we need.

To see how BeautifulSoup works, we’ll use the simple website example from earlier.
As a first step, we’ll load the `BeautifulSoup` package along with Pandas.

```python
from bs4 import BeautifulSoup
import pandas as pd
```

Let’s store the HTML content in a string variable named `example_html`.

```python
example_html = """
<!DOCTYPE html>
<html>
<head>
<title>Sample web page</title>
</head>
<body>
<h1>h1 Header #1</h1>
<p>This is a paragraph tag</p>
<h2>h2 Sub-header</h2>
<p>A new paragraph, now in the <b>sub-header</b></p>
<h1>h1 Header #2</h1>
<p>
This other paragraph has two hyperlinks,
one to <a href="https://carpentries.org/">The Carpentries homepage</a>,
and another to the
<a href="https://carpentries.org/workshops/past-workshops/">past workshops</a> page.
</p>
</body>
</html>
"""
```

We parse the HTML by passing it to the `BeautifulSoup()` function, specifying `html.parser` as the parser.
This creates an object that represents the document as a nested data structure —similar to the tree structure we discussed earlier.
Using the `.prettify()` method on this object displays the HTML with indentation that reflects its nested structure, making it easier to read.

```python
soup = BeautifulSoup(example_html, 'html.parser')
print(soup.prettify())
```

```output
<!DOCTYPE html>
<html>
 <head>
  <title>
   Sample web page
  </title>
 </head>
 <body>
  <h1>
   h1 Header #1
  </h1>
  <p>
   This is a paragraph tag
  </p>
  <h2>
   h2 Sub-header
  </h2>
  <p>
   A new paragraph, now in the
   <b>
    sub-header
   </b>
  </p>
  <h1>
   h1 Header #2
  </h1>
  <p>
   This other paragraph has two  hyperlinks, one to
   <a href="https://carpentries.org/">
    The Carpentries homepage
   </a>
   , and another to the
   <a href="https://carpentries.org/workshops/past-workshops/">
    past workshops
   </a>
   .
  </p>
 </body>
</html>
```

Now that our `soup` variable holds the parsed document, we can use the `.find()` and `.find_all()` methods to search for elements.

- `.find()` looks for the first occurrence of a specified tag and returns the entire element, including its opening and closing tags.

- If multiple elements share the same tag, `.find()` returns only the first one.

- To get all matching elements, use `.find_all()`, which returns a list of all elements with the specified tag.

- To extract just the text inside an element and all its children, use the `.get_text()` method.
`.find()` will search the tag that we specify, and return the entire element, including the starting and closing tags.

Below, you’ll see examples of how these commands work with our simple website.

```python
print("1.", soup.find('title'))
print("2.", soup.find('title').get_text())
print("3.", soup.find('h1').get_text())
print("4.", soup.find_all('h1'))
print("5.", soup.find_all('a'))
print("6.", soup.get_text())
```

```output
1. <title>Sample web page</title>
2. Sample web page
3. h1 Header #1
4. [<h1>h1 Header #1</h1>, <h1>h1 Header #2</h1>]
5. [<a href="https://carpentries.org/">The Carpentries homepage</a>, <a href="https://carpentries.org/workshops/past-workshops/">past workshops</a>]
6. 

Sample web page


h1 Header #1
This is a paragraph tag
h2 Sub-header
A new paragraph, now in the sub-header
h1 Header #2

This other paragraph has two hyperlinks,
one to The Carpentries homepage,
and another to the
past workshops page.
```

How would you extract all hyperlinks identified with `<a>` tags?
In our example, we see that there are only two hyperlinks, and we could extract them in a list using the `.find_all('a')` method.

```python
links = soup.find_all('a')
print("Number of hyperlinks found: ", len(links))
print(links)
```
```output
Number of hyperlinks found:  2
[<a href="https://carpentries.org/">The Carpentries homepage</a>, <a href="https://carpentries.org/workshops/past-workshops/">past workshops</a>]
```

To access the value of a given attribute in an element, for example the value of the `href` attribute in `<a href="">`, we would use the `.get()` method with the name of the attribute (i.e. `.get('href')`).
Let's make a loop that prints only the URL for each hyperlink we have in our example.

```python
for item in links:
    print(item.get('href'))
```
```output
https://carpentries.org/
https://carpentries.org/workshops/past-workshops/
```

::::::::::::::::::::::::::::::::::::: challenge

Create a Python dictionary that has the following three items, containing information about the **first** hyperlink in the HTML of our example.

```python
first_link = {
   'element': the complete hyperlink element,
   'url': the destination url of the hyperlink,
   'text': the text that the website displays as the hyperlink
}
```

:::::::::::::::::::::::: solution

One way of completing the exercise is as follows.

```python
first_link = {
   'element': str(soup.find('a')),
   'url': soup.find('a').get('href'),
   'text': soup.find('a').get_text()
}
```

An alternative and often more efficient approach is to first store the result of `soup.find('a')` in a variable, rather than calling it multiple times.
This makes your code cleaner and avoids redundant searches.

You can also start by creating an empty dictionary and then add key-value pairs to it. This is especially useful when you're extracting multiple pieces of information in a loop, as you'll likely want to build up a dictionary of results step by step.

```python
find_a = soup.find('a')
first_link = {}
first_link['element'] = str(find_a)
first_link['url'] = find_a.get('href')
first_link['text'] = find_a.get_text()
```
:::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::

To wrap up this introduction to HTML and BeautifulSoup, let’s write code that extracts all hyperlink elements in a structured way —capturing each link's tag, destination URL, and display text.

We’ll start with the links variable we created earlier: `links = soup.find_all('a')`.
Then, we’ll loop through each hyperlink element, store the three pieces of information in a dictionary, and append each dictionary to a list called `list_of_dicts`.
At the end, we’ll have a list containing two dictionaries —one for each link— which we can easily convert into a Pandas DataFrame.

```python
links = soup.find_all('a')
list_of_dicts = []
for item in links:
    dict_a = {}
    dict_a['element'] = str(item)
    dict_a['url'] = item.get('href')
    dict_a['text'] = item.get_text()
    list_of_dicts.append(dict_a)

links_df = pd.DataFrame(list_of_dicts)
print(links_df)
```

```output
                                             element                                                url                      text
0  <a href="https://carpentries.org/">The Carpent...                           https://carpentries.org/  The Carpentries homepage
1  <a href="https://carpentries.org/workshops/pas...  https://carpentries.org/workshops/past-workshops/            past workshops
```

You can find more detailed information about the BeautifulSoup package and its full range of methods in the [BeautifulSoup Documentation](https://beautiful-soup-4.readthedocs.io/en/latest/).

## The rights, wrongs, and legal barriers to scraping 

The internet isn’t as open as it once was.
What used to be a vast, freely accessible source of information has become a valuable reservoir of data —especially for training machine learning and generative AI models.
In response, many social media platforms and website owners have either started monetizing access to their data or taken steps to protect their resources from being overwhelmed by automated bots.

As a result, it’s increasingly common for websites to include explicit prohibitions against web scraping in their Terms of Service (TOS).
To avoid legal or ethical issues, it’s essential to check both the TOS and the site's `robots.txt` file before scraping.

You can usually find a site's `robots.txt` file by appending `/robots.txt` to the root of the domain—for example: `https://facebook.com/robots.txt` (not `https://facebook.com/user/robots.txt`).
Both the TOS and `robots.txt` will help you understand what is allowed and what isn’t, so it’s important to review them carefully before proceeding.


::::::::::::::::::::::::::::::::::::: challenge

Visit [Facebook's Terms of Service](https://www.facebook.com/terms.php) and its [robots.txt file](https://facebook.com/robots.txt). What do they say about web scraping or collecting data using automated means? Compare it to [Reddit's TOS](https://redditinc.com/policies/user-agreement) and [Reddit's robots.txt](https://www.reddit.com/robots.txt).

::::::::::::::::::::::::::::::::::::::::::::::::

In addition to reviewing a website’s policies, you should also be aware of the laws that apply in your region —especially those related to copyright and data privacy.
If you’re planning to collect a large amount of data for research or commercial purposes, it’s a good idea to seek legal advice before proceeding.
If you’re affiliated with a university, there’s a good chance it has a copyright office or legal team that can help you navigate the legal aspects of your project.
The university library is often a great starting point for finding support and guidance on copyright and data use.

To conclude, here is a brief code of conduct you should keep in mind when doing web scraping:


1. **Ask nicely whether you can access the data in another way**.
If your project relies on data from a particular organization, consider reaching out to them directly or checking whether they provide an API.
With a bit of luck, they might offer the data you need in a structured format —saving you time and effort.

1.  **Don’t download content that’s clearly not public**.
For example, academic journal publishers often impose strict usage restrictions on their databases. 
Mass-downloading PDFs can violate these rules and may get you —or your university librarian— into trouble.

    If you need local copies for a legitimate reason (e.g., text mining), special agreements may be possible.
Your university library is a good place to start exploring those options.

1. **Check your local legislation**.
Many countries have laws protecting personal information, such as email addresses or phone numbers.
Even if this data is visible on a website, scraping it could be illegal depending on your jurisdiction (e.g., in Australia).

1. **Don’t share scraped content illegally**.
Scraping for personal use is often considered fair use, even when it involves copyrighted material. But sharing that data —especially if you don’t have the rights to distribute it— can be illegal.

1. **Share what you can**.
If the scraped data is public domain or you’ve been granted permission to share it, consider publishing it for others to reuse (e.g., on datahub.io).
Also, if you wrote a scraper to access it, sharing your code (e.g., on GitHub) can help others learn from and build on your work.

1. **Publish your own data in a reusable way**.
Make it easier for others by offering your data in open, software-agnostic formats like CSV, JSON, or XML. 
Include metadata that describes the content, origin, and intended use of the data.
Ensure it’s accessible and searchable by search engines.

1.  **Don’t break the Internet**.
Some websites can’t handle high volumes of requests.
If your scraper is recursive (i.e., it follows links), test it first on a small subset.

    Be respectful by setting delays between requests and limiting the rate of access.
You’ll learn more about how to do this in the next episode.

Following these guidelines helps ensure that your scraping is ethical, legal, and considerate of the broader web ecosystem.

::::::::::::::::::::::::::::::::::::: keypoints 

- Every website is built on an HTML document that structures its content.
- An HTML document is composed of elements, usually defined by an opening `<tag>` and a closing `</tag>`.
- Elements can have attributes that define their properties, written as `<tag attribute_name="value">`.
- We can parse an HTML document using `BeautifulSoup()` and search for elements with the `.find()` and `.find_all()` methods.
    - We can extract the text inside an element with `.get_text()` and access attribute values using `.get("attribute_name")`.
- Always review and respect a website’s Terms of Service (TOS) before scraping its content.

::::::::::::::::::::::::::::::::::::::::::::::::
