# Purple HATS

Purple HATS is a customisable, automated accessibility testing tool that allows software development teams to assess whether their products are user-friendly to persons with disabilities (PWDs).

**Topics**  

- 


## Onboarding / Dedication of HATS Linux Elastic Agent

If you have onboarded SHIP-HATS previously, you would have been dedicated with the Linux elastic agent to do security scans with Fortify and/or SonarQube. You can use the same Linux agent for Purple HATS scan as well.

If you are new, please raise a HATS service request to request for dedication of elastic agent. Please provide the following information as well

Your project's Bamboo build project/ build plan

## Technical Queries

If you face difficulties in using Purple HATS, please raise a service request under Purple HATS - Accessibility Testing.



## Purple HATS Usage

The following is the Purple HATS CLI provided in the Bamboo elastic agent. If you are looking to running Purple HATS locally, you may refer to our GitHub repository at https://github.com/GovTechSG/purple-hats

## Running Scans on Local Web Projects

You can checkout your website project in the pipeline to run the scans. For NPM, you can use `start-server-and-test`. For other package manager, you may need to find an equivalent packages performing the same function.

Please include the following NPM script name in your package.json. In this case, the NPM script name, `scan`, has been defined in the package.json with the Purple HATS CLI command. 
The `ci` NPM script name is defined to be used in the pipeline.
In this walkthrough, a React project is being used to perform a website scan.




In your Bamboo build plan,

Please add `export CI=true` into the Script task to ensure the tool "start-server-and-test" or equivalent is able to run in the pipeline, before running the NPM scripts


## AXE to WCAG Mapping

Purple HATS is currently using AXE 3.5

We will be updating to use AXE 4.x which covers 2 more clauses (Highlighted in yellow)
Refer to AXE rules and remediation Advice here
Please note the following that Purple HATS also covers the following WCAG clauses while not included in the accessibility checks

- [WCAG 2.2.4 Link Purpose (Link Only)](https://www.w3.org/TR/UNDERSTANDING-WCAG20/navigation-mechanisms-link.html)
- [WCAG 2.4.9 Interruptions](https://www.w3.org/TR/UNDERSTANDING-WCAG20/time-limits-postponed.html)
- [WCAG 3.2.5 Change on Request](https://www.w3.org/TR/UNDERSTANDING-WCAG20/consistent-behavior-no-extreme-changes-context.html)

## WCAG2.1 success criteria from W3C, consists of Level AA except clause 1.2

Below is the AXE to WCAG mapping on the success criteria coverage for the accessibility checks. 

>**Note:** Following additional guidelines are available for accessibility checks marked with asterisks(*).

**1.1  Provide text alternatives for any non-text content**
|Success Criteria|AXE Rules Coverage|
|---|---|
|1.1.1  Provide text alternatives that serves the equivalent purpose for all non-text content so that it can be changed into other forms people need, such as large print, braille, speech, symbols or simpler language.|Y|

---

**1.2 Provide alternatives for time-based media (audio-video captions, transcripts, sign language)**
|Success Criteria|AXE Rules Coverage|
|---|---|
1.2.1   Provide alternative for prerecorded audio-only content, and alternative or audio track for prerecorded video-only content.|
1.2.2   Provide captions for all prerecorded audio content in synchronized media.|Y<br>(New in AXE 4.1)
1.2.3  Provide alternative or audio description of the prerecorded video content in   synchronized media.|Y<br>(New in AXE 4.1)

---

**1.3 Create content that can be presented in different ways (for example simpler layout) without losing information or structure**
|Success Criteria|AXE Rules Coverage|Notes
|---|---|--|
1.3.1 Information, structure, and relationships conveyed through presentation can be programmatically determined or are available in text.|Y|
1.3.2 When the sequence in which content is presented affects its meaning, a correct reading sequence can be programmatically determined.||
1.3.3 Instructions provided for understanding and operating content do not rely solely on sensory characteristics of components such as shape, size, visual location, orientation, or sound.||
1.3.4 *Content does not restrict its view and operation to a single display orientation, such as portrait or landscape, unless a specific display orientation is essential.|Y|Cannot force users of mobile devices to hold their devices in or rotate them to a certain orientation in order to see/use the content.
1.3.5 *The purpose of each input field collecting information about the user can be programmatically determined.|Y|A piece of code must be able to tell what is expected to be entered by a user or what’s the meaning of a piece of entered information. This will enable the browser to autofill input fields based on data previously entered by the user.

---

**1.4  Make it easier for users to see and hear content including separating foreground from background**
|Success Criteria|AXE Rules Coverage|
|---|---|
1.4.1   Color is not used as the only visual means of conveying information, indicating an action, prompting a response, or distinguishing a visual element.|Y
1.4.2   If any audio on a Web page plays automatically for more than 3 seconds, either a mechanism is available to pause or stop the audio, or a mechanism is available to control audio volume independently from the overall system volume level, or text part of a logo or brand name.|Y
1.4.3   The visual presentation of text and images of text has a contrast ratio of at least 4.5:1, except for large text, text or images of text that are part of an inactive user interface component.|Y
1.4.4  Except for captions and images of text, text can be resized without assistive technology up to 200 percent without loss of content or functionality.|Y
1.4.5   If the technologies being used can achieve the visual presentation, text is used to convey information rather than images of text.|
1.4.10 *Content can be presented without loss of information or functionality, and without requiring scrolling in two dimensions.|
1.4.11 *The visual presentation of the user interface components and graphical objects have a contrast ratio of at least 3:1 against adjacent color(s).|
1.4.12 *In content implemented using markup languages that support the following text style properties, no loss of content or functionality occurs by setting all of the following and by changing no other style property.|Y
1.4.13 *Where receiving and then removing pointer hover or keyboard focus, it triggers additional content to become visible and then hidden.|

---

**2.1  Make all functionality available from a keyboard**
|Success Criteria|AXE Rules Coverage|
|---|---|
2.1.1   All functionality of the content is operable through a keyboard interface without requiring specific timings for individual keystrokes, except where the underlying function requires input that depends on the path of the user's movement and not just the endpoints.|Y
2.1.2   If keyboard focus can be moved to a component of the page using a keyboard interface, then focus can be moved away from that component using only a keyboard interface, and, if it requires more than unmodified arrow or tab keys or other standard exit methods, the user is advised of the method for moving focus away.|
2.1.4 *If a keyboard shortcut is implemented in content using only letter (including upper- and lower-case letters), punctuation, number, or symbol characters, then a mechanism is available to turn the shortcut off, remap the shortcut or make it active only on focus.|

---

**2.2 Enough Time: Provide users enough time to read and use content. No timing, interruptions can be postponed or suppressed by the user except interruptions involving an emergency, when an authenticated session expires, the user can continue the activity without loss of data after re-authenticating**
|Success Criteria|AXE Rules Coverage|
|---|---|
2.2.1 For each time limit that is set by the content, allow user to turn off, adjust, or extend. No need for this if the time limit is a required of a real-time event, the time limit is essential, or the time limit is longer than 20 hours.|Y
2.2.2 For moving, blinking, scrolling, or auto-updating information, there is a mechanism for user to pause, stop, or hide it.|Y

---

**2.3 Seizures: Do not design content in a way that is known to cause seizures**
|Success Criteria|AXE Rules Coverage|
|---|---|
2.3.1   Web pages do not contain anything that flashes more than three times in any one second period, or the flash is below the general flash and red flash thresholds.|

---

**2.4  Provide ways to help users navigate, find content and determine where they are, bypass blocks, page titles, focus order, link purpose from text alone, breadcrumbs**
|Success Criteria|AXE Rules Coverage|
|---|---|
2.4.1  A mechanism is available to bypass blocks of content that are repeated on multiple Web pages.|Y
2.4.2   Web pages have titles that describe topic or purpose.|Y
2.4.3  If a Web page can be navigated sequentially and the navigation sequences affect meaning or operation, focusable components receive focus in an order that preserves meaning and operability.|
2.4.4   The purpose of each link can be determined from the link text alone or from the link text together with its programmatically determined link context, except where the purpose of the link would be ambiguous to users in general.|Y
2.4.5  More than one way is available to locate a Web page within a set of Web pages except where the Web Page is the result of, or a step in, a process.|
2.4.6  Headings and labels describe topic or purpose.|
2.4.7 Any keyboard operable user interface has a mode of operation where the keyboard focus indicator is visible.|Y

---

**2.5  Input Modalities: Make it easier for users to operate functionality through various inputs beyond keyboard.**
|Success Criteria|AXE Rules Coverage|
|---|---|
2.5.1 *All functionality that uses multipoint or path-based gestures for operation can be operated with a single pointer without a path-based gesture, unless a multipoint or path-based gesture is essential.|
2.5.2 *For functionality that can be operated using a single pointer, there is no down-event to execute the function, a mechanism to abort or undo the function after completion, up-event reverses preceding down-event, or completing the function on down-event is essential.|
2.5.3 *For user interface components with labels that include text or images of text, the name contains the text that is presented visually.|Y
2.5.4 *Functionality that can be operated by device motion or user motion can also be operated by user interface components and responding to the motion can be disabled to prevent accidental actuation.|

---

**3.1  Readable: make text content readable and understandable, identifying specific definitions of words or phrases used in an unusual or restricted way, including idioms and jargon, abbreviations, difficult pronunciations**
|Success Criteria|AXE Rules Coverage|
|---|---|
3.1.1 The default human language of each Web page can be programmatically determined.|Y
3.1.2 The human language of each passage or phrase in the content can be programmatically determined except for proper names, technical terms, words of indeterminate language, and words or phrases that have become  part of the vernacular of the immediately surrounding text.|Y

---

**3.2  Predictable: make web pages appear and operate in predictable ways, consistent navigation, consistent identification**
|Success Criteria|AXE Rules Coverage|
|---|---|
3.2.1  When any component receives focus, it does not initiate a change of context.|
3.2.2  Changing the setting of any user interface component does not automatically cause a change of context unless the user has been advised of the behavior before using the component.|
3.2.3  Navigational mechanisms that are repeated on multiple Web pages within a set of Web pages occur in the same relative order each time they are repeated, unless a change is initiated by the user.|
3.2.4  Components that have the same functionality within a set of Web pages are identified consistently.|

---

**3.3  Input Assistance: help users avoid and correct mistakes, prevention – reversible, checked, confirmed**
|Success Criteria|AXE Rules Coverage|
|---|---|
3.3.1  If an input error is automatically detected, the item that is in error is identified and the error is described to the user in text.|
3.3.2  Labels or instructions are provided when content requires user input.|Y
3.3.3  If an input error is automatically detected and suggestions for correction are known, then the suggestions are provided to the user, unless it would jeopardize the security or purpose of the content.|
3.3.4  For Web pages that cause legal commitments or financial transactions for the user to occur, that modify or delete user-controllable data in data storage systems, or that submit user test responses, ensure submissions are reversible, data is checked for input error and can be corrected, or a mechanism is available to review and confirm before submission.|

**4.1    Maximize compatibility with current and future user agents, including assistive technologies.**
|Success Criteria|AXE Rules Coverage|
|---|---|
4.1.1  Ensure elements have complete start and end tags, nested according to their specifications, do not contain duplicate attributes.|Y
4.1.2  Allows all user interface components name and role to be programmatically determined.|Y
4.1.3  *In content implemented using markup languages, status messages can be programmatically determined through role or properties such that they can be presented to the user by assistive technologies without receiving focus.|


