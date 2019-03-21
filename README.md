# Review

File: Test Page 2.html.html

Date:  March 20, 2019

As you mention, there are so many things wrong with the source file.  HTML, Accessibility, Broken Links, etc.   The page appears to be the output of a WYSIWYG editor circa 1998.  It needs recoding to Web Standards; not remediation.


# Tests
1. Content Review
2. HTML Validation: https://validator.w3.org/
3. WAVE Review



# Content Issues
1. Weak file naming: redundant extensions, spacing poor form  *.html.html.  File name is not compatible with all operating systems and mixed case increases input errors. Better:  test-page-2.html
1. Missing assets (as noted in email) logo and spacer gifs.
* Broken links
* Subject matter of page is unclear.  
* Missing page title or `H1` and purpose of main form is unclear.
* `<title>` value does not accurately describe purpose of page



## HTML Issues
__Failed HTML Validation (66 errors)__.  Generally, I stop here and send the page back to the developer to fix the HTML along with the validation report.  Even though modern browsers are highly fault tolerant,  if a page is non-standard HTML, it is not machine readable and therefore not Accessible.

This HTML is classic 1998 WYSIWYG output.  Some highlights:

  1. Missing DOCTYPE declaration
  * Missing encoding.  
  * Non-standard mixing of structure and presentation.  Use CSS instead of presentational attributes like `bgcolor`, `border`, `align` which are deprecated in HTML5. Also, shim or spacer gifs, `&nbsp;`,`<br>`  and `<hr>` for creating space; use CSS margin and padding.
  * Table based layouts.  Use tables for data not presentation.
  * Form inputs missing labels and or broken `for` references
  * Not using semantic markup for sectioning content.
  * broken form `<form name=search' and 6 orphaned`<input hidden` elements

## Accessibility Issues
__WAVE flagged 10 error and 19 warnings.__  But in my experience, if the HTML is invalid, then Accessibility review tools behave unpredictably.

  1. Purpose of page content is unclear.  Content does not tell a story. Page has not answered the basic Who, What, and Why questions.
  * Main Form (the one with most inputs) is unclear not title or description of purpose. 
  * Layout tables are painful.
  * Missing a means to jump to main content.
  * Missing alt text on graphic content.
  * Form inputs have missing labels and broken references.
  * Link label should describe target action/page.
  * Should use 'and' when the word is meant rather than an ampersand.
  * `<span id='nuanria_plugin_outer'`> block is not accessible.  Function of object is not clear.  Should research purpose and tagging options.  May need ARIA tagging.


## Remediation Advice
Follow HTML5 Coding Standards. [See HTML sample](test-page-2-better.html)

  * Research the purpose of the page.  What do we want the user to do?  What is the primary use case.  Then, re-write the copy to communicate the message, including
    * Page or form title: the `h1`
    * Optional additional context.
    * The secondary promotional copy.
  * Separate content and presentation.  
  * Declare doctype and encoding
  * Add 'meta name='veiwport'`` tag for better responsive design on mobile.
  * Add skip nav
  * Use HTML5 sectioning elements  
  * Recode NavBar as  a `<nav>` element and link list.  Use of `accesskey` attributes suggest these may have been intended as menu options; but menus are better fit for web applications.  Consider testing removal of `accesskey` attributes with user community.
    * Consider re-structuring the information architecture so the sitemap outline more clearly presents the offer to primary and secondary audiences.
  * 'Free Download' link is confusing and trouble.  Based on title value, it may be an promotion rather than a nav link.
    * IF promotion, should create separate section. for `free download` offer.  Edit copy so button label and instructions agree.  
    * IF part of sitemap, should rename link to better fit target page title: "InSight and InFocus Trial".
  * In general, follow W3C's recommended HTML5 Forms markup suggestions.
  * Clarify purpose of the orphan `hidden` input elements.
  * Search Form.
    * Method should be GET.  Use POST for adding/editing values.  
    * Input should be `type="search"` and  a `required` attribute (this will prevent null searches).  May use a placeholder text. And MUST have a `title='keyword'` in the absence of a label. May include `title` and/or 'x-moz-errormessage' to improve error messaging.
    * Button should use `<button type='submit>'` element instead of `<input type='submit'>` for greater control in presentation.

  * Main Form should use HTML5 forms.
    * Must have a section heading.  May have introduction:  data collection forms should make the purpose of data collection clear.
    * Input `type` should match data type for tel and email.
    * Required inputs MUST have `required` attributes.  They  may use `pattern` regex for validation, and placeholder aids. May include `title` and/or 'x-moz-errormessage' to improve error messaging.
    * The five optional inputs should be removed.  This is the data minimization principal of Privacy by Design.  Plus fewer inputs will lead to increased conversions.  However, if not removed:
    * All `<option>` elements must have `value` attributes
    * language `<option>` labels should use full name, not the language code, possibly in the appropriate language.
    * Assuming back-end needs separate month, day, year inputs, use a `<fieldset>` structure.
    * Submit button label should describe the user's need or objective.  Use `button` element for greater presentation control.
  * Page footer area
    * Should add a "Privacy" link in your footer.  You should have a clearly labeled, conspicuous link to a Privacy Policy on every landing page and pages collecting Personally Identifiable Information (PII)
    * Should clarify context for email and phone links.
    * May use `href='tel:'` link for phone number markup.
  * `<span id='nuanria_plugin_outer'`> may need ARIA tagging or alternate content. Function and behavior of object is unclear.  Should research purpose and tagging options.  

  * Presentation style
    * line height >= 1.5
    * input and button font-sizes to 1em
    * use media queries to manage mobile, tablet, and desktop differences.
    * design padding for touch links in mobile/tablet targets.
    * create system of link styles for header, footer, as well as normal body.
    * and lots more
