# Report 3- Researching Commands

## Command- `grep` 

<br /> Description: `grep`  is a command-line utility that stands for "global regular expression print." 
It is used to search for specific text patterns within files or directories. When you run grep, you provide it with a pattern to search for
, and it scans the specified files or directories to find lines that match that pattern. 
It then prints out those lines, allowing you to quickly identify and extract the relevant information you're looking for.


### Options

 `grep -i`
<br /> Description: the option ` -i` makes the search case-insenstive, allowing for matches even 
if the cases of the letters differ. 
<br /> Example 1: Searching for the word "terrorism" with `grep -i`:

Input: 
```
grep -i "terrorism" chapter-1.txt

```
 Output: 
```
'counterrorism.'
'occurring', terrorism would have to be
'cultural' theory of terrorism.

```
<br /> Explanation: The `-i` option allows grep to match words regardless of case, 
so it returns matches for both "terrorism" and "Terrorism."

<br /> Example 1: Searching for the word "semptember" with `grep -i`:

Input: 
```
grep -i "september" chapter-1.txt

```
Output:  (there are more lines but this is just some of the lines) 
```
September 11, 2001, was
attack on September 11, 2001.

```
<br /> Explanation: The `-i` option allows grep to match words regardless of case, 
so it returns matches for both "semptember" and "September."

<br /> `grep -v`
<br />Description: the opition `- v` inverts the matches, in other words, it displays teh lines that 
do not match the give chracters/patters. 

<br /> Example 1: Searching for lines that do not contian the words "terrorist" (the 's' is not included)
<br /> Input:
```
grep -v "terrorist" chapter-1.txt

```
Output:  (there are more lines but this is just some of the lines) 
```
terrorists are studying
is largely one of terrorists studying international relations
someone who fights terrorists is not a

```
<br />  Explanation: The `-v` option allows grep to match words that do not contian the words "terrorist" case inclusive. 
Hench terrorists was an output as it is not the same as terrorist 


<br /> Example 2: Searching for lines not containing the word "attack":
<br /> Intput:
```
grep -v "attack" chapter-1.txt

```
<br /> Output: (there are more lines but this is just some of the lines) 
```
hijacked airplane, the terrorists
the mindset of terrorists. These events
terrorize by sporadic attacks, producing horror,
the particular challenge of attacking a
terrorists to target commercial
Understanding why terrorists target the

```
<br />  Explanation: The `-v` option allows grep to match words that do not contian the words "attack" case inclusive. 

<br /> `grep -n`
<br /> Description: : This option displays line numbers along with the matched lines. 
<br /> Example 1: Searching for the word "terror" with line numbers:
<br /> Input: 
```
grep -n "terror" chapter-1.txt

```
Output: (there are more lines but this is just some of the lines) 

```
20:U.S. response to terror
21:Networks of terror
24:During the 1990s, terror-
25:It is through terror-
26:how terrorism affects

```
Explanation: The -n option causes grep to display line numbers for each matched line.

<br /> Example 2: Searching for the word "crisis" with line numbers:

<br /> Input:
```
Example 2: Searching for the word "crisis" with line numbers:

``` 
<br /> Output: (there are more lines but this is just some of the lines) 
```
97:of a national crisis. 
101:a time of crisis, and also
135:forces of the crisis. The

```
Explanation: The -n option causes grep to display line numbers for each matched line.

<br />`grep -r` 
<br /> Description: This option allows grep to search files recursively in directories.
<br /> Example 1: Searching for the word "intelligence" recursively in the current dictionary. 
<br /> Input:
```
grep -r "intelligence" 

```

<br /> Output: 
```
./chapter-1.txt:The U.S. intelligence community developed
./chapter-

```
<br /> Explanation: The -r option (or --recursive) in grep allows it to search for a specific pattern or word recursively within directories. 
In this example, the command grep -r "intelligence" . is executed in the current directory (.) to search for the word "intelligence" in all
files and subdirectories within the current directory.


<br /> Example 2: Searching for the word "attack" recursively in the current directory:

<br /> Input: 

```
grep -r "attack" .

```
Output: (there are more lines but this is just some of the lines) 
```
./chapter-1.txt:Widespread terror attacks involving
./chapter-1.txt:attacks were generally random
./chapter-1.txt:others, such as attacks on
./chapter-1.txt:pattern of catastrophic attacks
./chapter-1.txt:which these attacks occurred.
./chapter-1.txt:committed the first attack. 
./chapter-1.txt:the 1993 attack was
./chapter-1.txt:the 1998 embassy attacks in
./chapter-1.txt:attacks from such an

```
<br /> Explanation: The -r option (or --recursive) in grep allows it to search for a specific pattern or word recursively within directories. 
In this example, the command grep -r "attack" . is executed in the current directory (.) to search for the word "attack" in all files and
subdirectories within the current directory.












