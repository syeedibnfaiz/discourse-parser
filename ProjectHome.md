This is a full discourse parser that extracts explicit discourse relations from English text. It has models trained on both the PDTB and the Biomedical Discourse Relation Bank. So, it can be used for parsing discourse relations from biomedical text as well as general English text.

**Example:**
Consider the following text:
John will not come because he is sick. However, he may come tomorrow. So, we are going to talk about it tomorrow.

The output for this text would be the following:
```
Sent-0: John will not come because he is sick .
Conn: because   [4,4]
Sense: Contingency
Arg2Head: is    6
Arg1Head: will  [0,1]

Sent-1: However , he may come tomorrow .
Conn: However   [0,0]
Sense: Comparison
Arg2Head: may   3
Arg1Head: will  [0,1]

Sent-2: So , we are going to talk about it tomorrow .
Conn: So        [0,0]
Sense: Contingency
Arg2Head: going 4
Arg1Head: may   [1,3]

The output follows the following format:
Sent-<Sentence#>: <Token 0> SPACE <Token 1> ... <Token (n-1)>
Conn: <Connective> TAB [<Start Token#>,<End Token#>]
Sense: <Sense>
Arg2Head: <Arg2 Head Token> TAB <Arg2 Head Token#>
Arg1Head: <Arg1 Head Token> TAB [<Arg1 Sentence#>,<Arg1 Head Token#>]
NewLine
```