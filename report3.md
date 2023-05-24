# Report 3- Researching Commands

## Command- `grep` 

<br /> Description: `grep`  is a command-line utility that stands for "global regular expression print." 
It is used to search for specific text patterns within files or directories. When you run grep, you provide it with a pattern to search for
, and it scans the specified files or directories to find lines that match that pattern. 
It then prints out those lines, allowing you to quickly identify and extract the relevant information you're looking for.

<br /> [Reference: man7.org ] (https://man7.org/linux/man-pages/man1/grep.1.html)  

### Options

#### `grep -i`
<br /> Description: the option ` -i` makes the search case-insenstive, allowing for matches even 
if the cases of the letters differ. 

<br /> [Reference: man7.org ] (https://man7.org/linux/man-pages/man1/grep.1.html)  

<br /> Example 1: Searching for the word "Excellent" with `grep -i`:

Input: 
```
$ grep -i "Excellent" stringsearch-data/technical/plos/pmed.0020191.txt 

```

 Output: 
```
The excellent article by Jordan Paradise, Lori B. Andrews, and colleagues, “Ethics

```
<br /> Explanation: The `-i` option allows grep to match words regardless of case, 
so it returns matches for both "Excellent" and "excellent."

<br /> Example 2: Searching for the word "Article" with `grep -i`:

Input: 
```
$ grep -i "Article" stringsearch-data/technical/plos/pmed.0020191.txt

```
Output:  
```
The excellent article by Jordan Paradise, Lori B. Andrews, and colleagues, “Ethics.

```
<br /> Explanation: The `-i` option allows grep to match words regardless of case, 
so it returns matches for both "Article" and "article."

#### `grep -v`
<br />Description: the opition `- v` inverts the matches, in other words, it displays the lines that 
do not match the give chracters/patterns. 

<br /> [Reference: man7.org ] (https://man7.org/linux/man-pages/man1/grep.1.html)  

<br /> Example 1: Searching for lines that do not contian the words "article" 
<br /> Input:
```
grep -v "article" stringsearch-data/technical/plos/pmed.0020191.txt

```
Output: 
```
  Constructing Ethical Guidelines for Biohistory” [1], neither advocates nor argues against
        biohistorical research; instead, it points out that such investigations are currently
        taking place without guidelines—ethical, scientific, moral, or religious. The question
        remains: if such guidelines were to be established, what individuals, 
institutions,
        governments, medical examiners, family members, or intrepid biographers are to be given
        permission? Who is to decide what is “historically significant”? Not to mention the
        meta-question: who is to decide who is to decide? I apologize to the authors if my brief
        comments [2] implied that they took a position on this issue.

```
<br />  Explanation: The `-v` option allows grep to match words that do not contian the words "article" case inclusive. 


<br /> Example 2: Searching for lines not containing the word  "Constructing":
<br /> Intput:
```
grep -v "Constructing" stringsearch-data/technical/plos/pmed.0020191.txt

```
<br /> Output: 
```

        The excellent article by Jordan Paradise, Lori B. Andrews, and colleagues, “Ethics.
        biohistorical research; instead, it points out that such investigations are currently
        taking place without guidelines—ethical, scientific, moral, or religious. The question
        remains: if such guidelines were to be established, what individuals, 
institutions,
        governments, medical examiners, family members, or intrepid biographers are to be given
        permission? Who is to decide what is “historically significant”? Not to mention the
        meta-question: who is to decide who is to decide? I apologize to the authors if my brief
        comments [2] implied that they took a position on this issue.

```
<br />  Explanation: The `-v` option allows grep to match words that do not contian the words "Constructing" case inclusive. 

#### `grep -n`
<br /> Description: : This option displays line numbers along with the matched lines. 

<br /> [Reference: man7.org ] (https://man7.org/linux/man-pages/man1/grep.1.html)  

<br /> Example 1: Searching for the word "Constructing" with line numbers:
<br /> Input: 
```
grep -n "Constructing" stringsearch-data/technical/plos/pmed.0020191.txt


```
Output:

```
7: Constructing Ethical Guidelines for Biohistory” [1], neither advocates nor argues against

```
Explanation: The -n option causes grep to display line numbers for each matched line. In this 
case it was line 7 that matched "Constructing."

<br /> Example 2: Searching for the word "Lori B. Andrews" with line numbers:

<br /> Input:
```
grep -n "Lori B. Andrews" stringsearch-data/technical/plos/pmed.0020191.txt

``` 
<br /> Output: 
```
6: The excellent article by Jordan Paradise, Lori B. Andrews, and colleagues, “Ethics.

```
Explanation: The -n option causes grep to display line numbers for each matched line. In this 
case it was line 6 that matched "Constructing.


#### `grep -r` 
<br /> Description: This option allows grep to search files recursively in directories.

<br /> [Reference: man7.org ] (https://man7.org/linux/man-pages/man1/grep.1.html)  

<br /> Example 1: Searching for the word "Lori B. Andrews" recursively in the current dictionary. 
<br /> Input:
```
grep -r "Lori B. Andrews" stringsearch-data/technical

```

<br /> Output: 
```
stringsearch-data/technical/plos/pmed.0020191.txt:        The excellent article by Jordan Paradise, Lori B. Andrews, and colleagues, “Ethics.
stringsearch-data/technical/plos/pmed.0020192.txt:        Science piece with Lori B. Andrews that Hayden references, I am troubled

```
<br /> Explanation: The -r option (or --recursive) in grep allows it to search for a specific pattern or word recursively within directories. 
In this example, the command grep -r "Lori B. Andrews" . is executed in the current directory (.) to search for the word "Lori B. Andrews" in all
files and subdirectories within the current directory.


<br /> Example 2: Searching for the word "Ethics" recursively in the current directory:

<br /> Input: 

```
grep -r "Ethics" stringsearch-data/technical

```
Output: 
```
stringsearch-data/technical/biomed/1471-2431-3-4.txt:          Ethics
stringsearch-data/technical/biomed/1471-2431-3-5.txt:          Ethics
stringsearch-data/technical/biomed/1472-6823-2-2.txt:          Ethics
stringsearch-data/technical/biomed/1472-684X-1-5.txt:        end-of-life care, the Institute for Ethics at the American
stringsearch-data/technical/biomed/1472-684X-2-1.txt:            discussion: Ethics and Discharge Planning (EDP) rounds.
stringsearch-data/technical/biomed/1472-684X-2-2.txt:        the EAPC Ethics Task Force "terminal' or 'palliative'
stringsearch-data/technical/biomed/1475-2883-2-11.txt:          Dame Institutional Review Boards, and the Ethics
stringsearch-data/technical/biomed/ar750.txt:          Ethics Committee of Jyväskylä Central Hospital approved
stringsearch-data/technical/biomed/cc1477.txt:        were used. Approval from the hospital Ethics Committee was
stringsearch-data/technical/biomed/cc1882.txt:        protocol was approved by the local Ethics Committee and the
stringsearch-data/technical/biomed/cc2172.txt:          Ethics Committee of Istanbul University Hospital. Written
stringsearch-data/technical/government/About_LSC/commission_report.txt:Professional Responsibility, the Canon of Ethics, and the high
stringsearch-data/technical/government/About_LSC/Protocol_Regarding_Access.txt:Unique State Ethics Rules: LSC acknowledges that there
stringsearch-data/technical/government/Media/Assuring_Underprivileged.txt:Committee, the American Bar Association's Ethics 2000 Commission
stringsearch-data/technical/plos/journal.pbio.0020150.txt:        the Stanford Center for Biomedical Ethics, thinks some action is warranted now, if only tostringsearch-data/technical/plos/pmed.0020191.txt:        The excellent article by Jordan Paradise, Lori B. Andrews, and colleagues, “Ethics.
stringsearch-data/technical/plos/pmed.0020192.txt:        by her comment on our article. Nowhere in that article, “Ethics. Constructing Ethical

```
<br /> Explanation: The -r option (or --recursive) in grep allows it to search for a specific pattern or word recursively within directories. 
In this example, the command grep -r "Ethics" . is executed in the current directory (.) to search for the word "Ethics" in all files and
subdirectories within the current directory.












