# Lab Report 4 -Editing from the Command Line: vim

## Step 1 -  Logging into ieng6 

```
ssh aqnguyen@ieng5.ucsd.edu 
enter password: xxxxxxxxxxxx

```

## Step 2 - Clone your fork of the repository from your Github account

```
[aqnguyen@ieng6-203]:~:284$ git clone https://github.com/gluconeogenewiz/lab7
Cloning into 'lab7'...
remote: Enumerating objects: 55, done.
remote: Counting objects: 100% (20/20), done.
remote: Compressing objects: 100% (16/16), done.
remote: Total 55 (delta 8), reused 12 (delta 4), pack-reused 35
Receiving objects: 100% (55/55), 376.53 KiB | 1.16 MiB/s, done.
Resolving deltas: 100% (20/20), done.
[aqnguyen@ieng6-203]:~:285$ 

```

## Step 3 - Run the tests, demonstrating that they fail 

```
[aqnguyen@ieng6-203]:lab7:286$ bash test.sh 
JUnit version 4.13.2
..E
Time: 0.527
There was 1 failure:
1) testMerge2(ListExamplesTests)
org.junit.runners.model.TestTimedOutException: test timed out after 500 milliseconds
        at ListExamples.merge(ListExamples.java:44)
        at ListExamplesTests.testMerge2(ListExamplesTests.java:19)

FAILURES!!!
Tests run: 2,  Failures: 1


```

## Step 4 - Edit the code file ListExamples.java to fix the failing test 
 <br /> Before 
```
import java.util.ArrayList;
import java.util.List;

interface StringChecker { boolean checkString(String s); }

class ListExamples {

  // Returns a new list that has all the elements of the input list for which
  // the StringChecker returns true, and not the elements that return false, in
  // the same order they appeared in the input list;
  static List<String> filter(List<String> list, StringChecker sc) {
    List<String> result = new ArrayList<>();
    for(String s: list) {
      if(sc.checkString(s)) {
        result.add(0, s);
      }
    }
    return result;
  }


  // Takes two sorted list of strings (so "a" appears before "b" and so on),
  // and return a new list that has all the strings in both list in sorted order.
  static List<String> merge(List<String> list1, List<String> list2) {
    List<String> result = new ArrayList<>();
    int index1 = 0, index2 = 0;
    while(index1 < list1.size() && index2 < list2.size()) {
      if(list1.get(index1).compareTo(list2.get(index2)) < 0) {
        result.add(list1.get(index1));
        index1 += 1;
      }
      else {
        result.add(list2.get(index2));
        index2 += 1;
      }
    }
    while(index1 < list1.size()) {
      result.add(list1.get(index1));
      index1 += 1;
    }
    while(index2 < list2.size()) {
      result.add(list2.get(index2));
      // change index1 below to index2 to fix test
      index1 += 1;
    }
    return result;
  }


}


```

<br /> Changes: Moved down to line 44, placed cursor on the 1 of index1 then clicked i ,
then clicked 2 to insert 2 in front of index making it index21, then clicking esc, then moving the cursor back on 1 and clicked x to delete it 
 
<br /> After

```
import java.util.ArrayList;
import java.util.List;

interface StringChecker { boolean checkString(String s); }

class ListExamples {

  // Returns a new list that has all the elements of the input list for which
  // the StringChecker returns true, and not the elements that return false, in
  // the same order they appeared in the input list;
  static List<String> filter(List<String> list, StringChecker sc) {
    List<String> result = new ArrayList<>();
    for(String s: list) {
      if(sc.checkString(s)) {
        result.add(0, s);
      }
    }
    return result;
  }


  // Takes two sorted list of strings (so "a" appears before "b" and so on),
  // and return a new list that has all the strings in both list in sorted order.
  static List<String> merge(List<String> list1, List<String> list2) {
    List<String> result = new ArrayList<>();
    int index1 = 0, index2 = 0;
    while(index1 < list1.size() && index2 < list2.size()) {
      if(list1.get(index1).compareTo(list2.get(index2)) < 0) {
        result.add(list1.get(index1));
        index1 += 1;
      }
      else {
        result.add(list2.get(index2));
        index2 += 1;
      }
    }
    while(index1 < list1.size()) {
      result.add(list1.get(index1));
      index1 += 1;
    }
    while(index2 < list2.size()) {
      result.add(list2.get(index2));
      // change index1 below to index2 to fix test
      index2 += 1;
    }
    return result;
  }


}

```

 ## Step 5 - Run the tests, demonstrating that they now succeed
 
 ```
 JUnit version 4.13.2
..
Time: 0.016 

OK (2 tests)
 ```
 
 ## Step 6 - Commit and push the resulting change to your Github account 
 
 git commit -m `` <message>`` 
  
 ```
 [aqnguyen@ieng6-203]:lab7:308$ git commit -m changes 
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   ListExamples.java

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        ListExamples.class
        ListExamplesTests.class
        StringChecker.class

no changes added to commit (use "git add" and/or "git commit -a")

 ```
 
 git commit -m part 2 ? 
 
 ```
 [aqnguyen@ieng6-203]:lab7:293$ git commit -m Changes
[main 74e6384] Changes
 Committer: Albert Nguyen <aqnguyen@ieng6-203.ucsd.edu>
Your name and email address were configured automatically based
on your username and hostname. Please check that they are accurate.
You can suppress this message by setting them explicitly. Run the
following command and follow the instructions in your editor to edit
your configuration file:

    git config --global --edit

After doing this, you may fix the identity used for this commit with:

    git commit --amend --reset-author

 4 files changed, 1 insertion(+), 1 deletion(-)
 create mode 100644 ListExamples.class
 create mode 100644 ListExamplesTests.class
 create mode 100644 StringChecker.class
 
 ```

git push 

```


```
