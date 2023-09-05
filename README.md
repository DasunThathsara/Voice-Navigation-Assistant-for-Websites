# Voice navigation assistant for websites
Its a voice navigation assistant. It helps to navigate through the pages in the website

<br /><br />
## How to run?
First, select the [index.html](https://github.com/DasunThathsara/User-defined-Regex/tree/main/Python) file and open it. When it open, browser popups a message to get user permissions for on the microphone. Click `Allow` button and give the access to the web page to use microphone. Now, the initial setup is over. If you want to activate the assistant, say `Hello Assistant`. Then the assistant was activated and you can say go to dashboard, go to settings like wise. After the saying, page automatically navigates that pages. When we activated the assistant and didn't say anything to assistant until 10 seconds, assistant will automatically turn off.

<br />

You can change this text file name to your own file name.
```python
text = open("test cases/text.txt", 'r')
pattern = open("test cases/pattern.txt", 'r')
output = open("results/patternmatch.output", 'w')
```

`regularExpression.py` contains the Regex file, and the main file imports functions from the `regularExpression.py` file.
<br/><br/>
#
First, import `regularExpression.py` and set the alias to re. Because `regularExpression` is too long and hard to handle.
```python
import regularExpression as re
```

<br /><br />

## Methodology
I use the `Knuth-Morris-Pratt (KMP)` algorithm to implement this and filter the pattern using simple if statements. Also, the matiching condition is called to the relevant function, and the output is given as a Boolean value.

```python
def search(String, Pattern):
    # --------------------- Find Either Or relation --------------------
    if any(i == '|' for i in Pattern):
        return search(String, Pattern.split('|')[0]) or search(String, Pattern.split('|')[1])


    # ---- Find if String starts with Pattern and ends with Pattern ----
    elif any(i == '?' for i in Pattern):
        if Pattern[-1] == '?':
            return search(String, Pattern.split('?')[0]) or search(String, Pattern.split('?')[0][:len(Pattern.split('?')[0]) - 1])
        elif Pattern[0] == '?':
            return search(String, Pattern.split('?')[1]) or search(String, Pattern.split('?')[1][1:])
        else:
            return search(String, Pattern.split('?')[0][-1] + Pattern.split('?')[1][0]) or search(String, Pattern.split('?')[0][-1][:len(Pattern.split('?')[0][-1]) - 1] + Pattern.split('?')[1][0])


    # ---- Find if String starts with Pattern and ends with Pattern ----
    elif Pattern[0] == "^" and Pattern[-1] == "$":
        return kmp(String, "".join(Pattern[1: len(Pattern) - 1])) and len(String) == len(Pattern) - 2


    # --------------- Find if String starts with Pattern ---------------
    elif Pattern[0] == "^":
        return kmp(String[: len(Pattern) - 1], "".join(Pattern[1:]))


    # ---------------- Find if String ends with Pattern ----------------
    elif Pattern[-1] == "$":
        return kmp(String[len(String) - len(Pattern) + 1:], "".join(Pattern[0: len(Pattern) - 1])) and search(String, "".join(Pattern[:len(Pattern) - 1]))


    return kmp(String, Pattern)
```

In this version, the program recognizes `^` `|` `$` `?` as the regex character.

<br><br>
*If you want to clone and run this code, open the Python folder in your IDE and run. Please use Python 3.9.


____
<p align="center">
    <a href="https://github.com/UltiRequiem/python-projects-for-intermediates/blob/main/LICENSE">
      <img alt="License: MIT" src="https://black.readthedocs.io/en/stable/_static/license.svg">
    </a
    &nbsp;
    <a href="https://hits.sh/github.com/DasunThathsara/User-defined-Regex/">
      <img alt="Hits" src="https://hits.sh/github.com/DasunThathsara/User-defined-Regex.svg?label=Views"/>
    </a>
    <a href="https://github.com/DasunThathsara/User-defined-Regex/actions">
      <img alt="Tests Passing" src="https://github.com/anuraghazra/github-readme-stats/workflows/Test/badge.svg" />
    </a>
  </p>
