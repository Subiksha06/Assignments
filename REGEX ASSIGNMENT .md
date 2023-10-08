```python
import regex as re 
```


```python
#1
text = "Python Exercises, PHP exercises."
str = "happy excited"
pattern = r"[.,\s+]" 
result = re.sub(pattern,":",text)
result1 = re.sub(pattern,":",str)
print(result)
print(result1)
```

    Python:Exercises::PHP:exercises:
    happy:excited
    


```python
#2
text = "anna eagerly awaited an exciting adventure in the enchanted forest."
text1 = "apples are recommended by doctors to eat when we are sick"
pattern = r"a\w+ | e\w+" 
match = re.findall(pattern, text)
match1 = re.findall(pattern, text1)
print(match)
print(match1)
```

    ['anna ', 'agerly ', 'awaited ', 'an ', 'adventure ', ' enchanted']
    ['apples ', 'are ', ' eat', 'are ']
    


```python
#3
text = "anna eagerly awaited an exciting adventure in the enchanted forest."
pattern = r"\w{4,}"
regex = re.compile(pattern)
matches = regex.findall(text)
for match in matches:
    print(match)

    

```

    anna
    eagerly
    awaited
    exciting
    adventure
    enchanted
    forest
    


```python
#4
text = "The artist paint a beautiful landscape with exquisite colors"
pattern = r"\b\w{3,5}\b"
regex = re.compile(pattern)
matches = regex.findall(text)
for match in matches:
    print(match)
```

    The
    paint
    with
    


```python
#5
string = ["example (.com)", "hr@fliprobo (.com)", "github (.com)", "Hello (Data Science World)", "Data (Scientist)"]
pattern = r"[()]"
regex = re.compile(pattern)
new_string = [regex.sub('',s) for s in string]
for x in new_string:
    print(x)
```

    example .com
    hr@fliprobo .com
    github .com
    Hello Data Science World
    Data Scientist
    


```python
#6
with open (r"C:\Users\DELL\Documents\url file.txt") as file:
    for line in file :
        pattern = r'\([^)]*\)'
        regex = re.compile(pattern)
        new_string = [regex.sub('',s) for s in string]  
        for x in new_string:
            print(x)
        

```

    example 
    hr@fliprobo 
    github 
    Hello 
    Data 
    


```python
#7
text = "ImportanceOfRegularExpressionsInPython"
pattern = r"(?=[A-Z])"
match = re.split(pattern,text) 
filtered_result = list(filter(None, match))

print(filtered_result)

```

    ['Importance', 'Of', 'Regular', 'Expressions', 'In', 'Python']
    


```python
#8
text = "RegularExpression1IsAn2ImportantTopic3InPython"
pattern = r"(?=[0-9])"
regex = re.compile(pattern)
match = regex.sub(" ",text)
print(match)
```

    RegularExpression 1IsAn 2ImportantTopic 3InPython
    


```python
#9 
def newfunction(text):
    pattern = r"(?=[A-Z])|(?=[0-9])"
    regex = re.compile(pattern)
    result = regex.sub(" ",text)
    return result 
    
text = "RegularExpression1IsAn2ImportantTopic3InPython" 
new = newfunction(text)
print(new)

    
```

     Regular Expression 1 Is An 2 Important Topic 3 In Python
    


```python
#10 
with open (r"C:\Users\DELL\Documents\email file.txt") as file:
    for line in file:
        pattern = "[a-zA-Z.]+@+[a-zA-Z.]+\w{2,}"
        regex = re.compile(pattern)
        match = regex.findall(line) 
        for x in match:
            print(x)
```

    xyz@domain.com
    xyz.abc@sdomain.domain.com
    hr@fliprobo.com
    


```python
#11 
def newfunct(string):
    pattern = r"^[A-Za-z0-9_]+$"
    result = re.search(pattern,string) 
    return result 

a = "winter_happy123"
b = "@34"
c = "sweater_winter45"

print(newfunct(a))
print(newfunct(b))
print(newfunct(c))
```

    <regex.Match object; span=(0, 15), match='winter_happy123'>
    None
    <regex.Match object; span=(0, 16), match='sweater_winter45'>
    


```python
#12 Match string that starts with 12 
def newfunct(string):
    pattern = r"^12\w+"
    result = re.match(pattern,string) 
    return result 

a = "12happy string"
b = "happy tsring"
c = "12sad string"

print(newfunct(a))
print(newfunct(b))
print(newfunct(c))
```

    <regex.Match object; span=(0, 7), match='12happy'>
    None
    <regex.Match object; span=(0, 5), match='12sad'>
    


```python
#13 
text = "192.003.001.045"
pattern =r"(\b0+)(\d+)\b"
result = re.sub(pattern,r"\2",text)
print(result)
```

    192.3.1.45
    


```python
#14 
with open(r"C:\Users\DELL\Documents\date file.txt") as file:
    for line in file:
        pattern =r'\b(?:January|February|March|April|May|June|July|August|September|October|November|December)\s+\d{1,2}\s+\d{4}\b'
        results = re.findall(pattern, line)
        print(results) 
```

    ['August 15 1947', 'October 06 2000']
    


```python
#15 
text = "The quick brown fox jumps over the lazy dog"
tosearch_strings=["quick","jumps","lazy","hyu"]
for x in tosearch_strings:
    pattern = re.escape(x)
    match = re.findall(pattern,text)
    if match:
        print(match) 
    else:
        print("not found")
    
```

    ['quick']
    ['jumps']
    ['lazy']
    not found
    


```python
#16
text = "The quick brown fox jumps over the lazy dog"
tosearch_strings=["quick","jumps","lazy","hyu"]
for x in tosearch_strings:
    pattern = re.escape(x)
    match = re.search(pattern,text)
    print(match)
    

```

    <regex.Match object; span=(4, 9), match='quick'>
    <regex.Match object; span=(20, 25), match='jumps'>
    <regex.Match object; span=(35, 39), match='lazy'>
    None
    


```python
#17 
text = 'Python exercises, PHP exercises, C# exercises'
pattern = "exercises" 
match = re.findall(pattern,text)
print(match)


```

    ['exercises', 'exercises', 'exercises']
    


```python
#18 
text = 'Python exercises, PHP exercises, C# exercises'
pattern = "exercises" 
result = re.finditer(pattern,text)
for x in result:
    print(x)
```

    <regex.Match object; span=(7, 16), match='exercises'>
    <regex.Match object; span=(22, 31), match='exercises'>
    <regex.Match object; span=(36, 45), match='exercises'>
    


```python
#19
text = "2023-10-05"
pattern = r"(\d{4})-(\d{1,2})-(\d{1,2})"
result = re.sub(pattern,r"\3-\2-\1",text)
print(result)
```

    05-10-2023
    


```python
#20 
text = "01.12 0132.123 2.31875 145.8 3.01 27.25 0.25"
pattern = r"[0-9]+\.[0-9]{1,2}"
result = re.findall(pattern,text)
print(result)
```

    ['01.12', '0132.12', '2.31', '145.8', '3.01', '27.25', '0.25']
    


```python
#21
text = "there are 6 apples, 5 mangoes and 234 grapes"
pattern = "\d+"
result = re.finditer(pattern,text)
for x in result:
    print(x)
```

    <regex.Match object; span=(10, 11), match='6'>
    <regex.Match object; span=(20, 21), match='5'>
    <regex.Match object; span=(34, 37), match='234'>
    


```python
#22
text = 'My marks in each semester are: 947, 896, 926, 524, 734, 950, 642'
pattern = "\d+"
result = re.findall(pattern,text)
max_var = result[0]
for num in result:
    if num > max_var:
        max_var = num    
print(max_var)

```

    950
    


```python
#23 
text = "RegularExpressionIsAnImportantTopicInPython"
pattern = r"(?=[A-Z])"
result = re.sub(pattern," ",text)
print(result)
```

     Regular Expression Is An Important Topic In Python
    


```python
#24
text = "Slow and Steady wins the Race"
pattern = r"[A-Z]\w+"
result = re.finditer(pattern,text)
for x in result:
    print(x)
```

    <regex.Match object; span=(0, 4), match='Slow'>
    <regex.Match object; span=(9, 15), match='Steady'>
    <regex.Match object; span=(25, 29), match='Race'>
    


```python
#25 
text = "This is is an amazing amazing experience"
pattern = r"(\w+)\s+\1"
result = re.sub(pattern,r"\1",text)
print(result)

```

    This is an amazing experience
    


```python
#26 
input_str = "This is is an amazing amazing experience $"
pattern = r"\w$"
if re.search(pattern,input_str):
    print(input_str)
else:
    print("not found")
```

    not found
    


```python
#27 
text = r"""RT @kapil_kausik: #Doltiwal I mean #xyzabc is "hurt" by #Demonetization as the same has rendered USELESS <ed><U+00A0><U+00BD><ed><U+00B1><U+0089> "acquired funds" No wo"""
pattern = r"#\w+"
result = re.findall(pattern,text)
print(result)
```

    ['#Doltiwal', '#xyzabc', '#Demonetization']
    


```python
#28 
text = "@Jags123456 Bharat band on 28??<ed><U+00A0><U+00BD><ed><U+00B8><U+0082>Those who  are protesting #demonetization  are all different party leaders"
pattern = r"<U\+[A-Z0-9]+>"
result = re.sub(pattern,"",text)
print(result)
```

    @Jags123456 Bharat band on 28??<ed><ed>Those who  are protesting #demonetization  are all different party leaders
    


```python
#29 
with open(r"C:\Users\DELL\Documents\qn29.txt")as file:
    for line in file:
        pattern = r"\d{1,2}-\d{1,2}-\d{1,2}"
        result = re.findall(pattern,line)
        print(result)
```

    ['12-09-19', '15-12-19']
    


```python
def lastfun(text):
    pattern = r"\b(\w{2,4})\b"
    regex = re.compile(pattern)
    result = regex.sub("",text)
    return result 

a="The following example creates an ArrayList with a capacity of 50 elements. 4 elements are then added to the ArrayList and the ArrayList is trimmed accordingly."
print(lastfun(a))
    
```

     following example creates  ArrayList  a capacity   elements. 4 elements   added   ArrayList   ArrayList  trimmed accordingly.
    
