# Voice navigation assistant for websites
Its a voice navigation assistant. It helps to navigate through the pages in the website


## How to run?
First, select the [index.html](https://github.com/DasunThathsara/Voice-Navigation-Assistant-for-Websites/tree/main/index.html) file and open it. When it opens, the browser pops up a message to get user permissions for the microphone. Click the `Allow` button and give access to the web page to use the microphone. Now, the initial setup is over. If you want to activate the assistant, say `Hello Assistant`. Then the assistant was activated, and you can say, Go to dashboard, Go to settings, etc. After the saying, the page automatically navigates to those pages. When we activate the assistant and don't say anything to it for 10 seconds, it will automatically turn off.

<br />

## How to add navigations?
You can add navigations to the assistant by changing text and links. Go to the [script.js](https://github.com/DasunThathsara/Voice-Navigation-Assistant-for-Websites/tree/main/script.js) file and edit following code set.
```javascript
if (transcript.includes('go to google')) {
    window.location.href = 'https://www.google.lk';
    output.innerText = 'Opening Google.lk.';
}
```

Dou you want to add more pages, add `else if` statements.
<br/><br/>


## Methodology
I use the `webkitSpeechRecognition` javascript library for implement this and it is a built in function. You can run this only in the `Chrome`, `Edge` and `Firefox` only.

____

[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
<a href="https://hits.sh/github.com/DasunThathsara/Voice-Navigation-Assistant-for-Websites/">
    <img alt="Hits" src="https://hits.sh/github.com/DasunThathsara/Voice-Navigation-Assistant-for-Websites.svg?label=Views"/>
</a>
<a href="https://github.com/DasunThathsara/Voice-Navigation-Assistant-for-Websites/actions">
    <img alt="Tests Passing" src="https://github.com/anuraghazra/github-readme-stats/workflows/Test/badge.svg" />
</a>
