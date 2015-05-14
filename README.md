# Welcome to ALM Search!

Searching for what you’re looking for in millions of lines of code can be pretty daunting. This wiki lists several functionalities to help users find everything easily and getting to it quickly. You may launch search from the 'Search' hub or using the search box on the 'Code/Explorer' tab within a project. 

## Query Syntax
Start searching for code using simple word queries. To further expand or narrow down your queries use the advanced search features described below. 

### Basic Search

|            Example search            |                                              Finds code containing...                                              |
|:------------------------------------:|:------------------------------------------------------------------------------------------------------------------:|
| QueueJobsNow                         | 'QueueJobsNow'                                                                                                     |
| QueueJobsNow   VSOnline              | both words 'QueueJobsNow' and 'VSOnline'                                                                           |
| "JobPriorityLevel priorityLevel"     | words 'JobPriorityLevel' and 'priorityLevel' such that 'priorityLevel' comes immediately after 'JobPriorityLevel'  |

### Scope filters
Narrow down your search results to a particular project, repository, file extension or path. You may also use the project and repository filters appearing in the left pane. 

| Scope filter  |  Example search                                     |  Finds code containing...                                        |
|---------------|-----------------------------------------------------|------------------------------------------------------------------|
|     Proj      |  QueueJobsNow proj:VSOnline                         |  'QueueJobsNow' inside projects named 'VSOnline'                 |
|     Repo      |  QueueJobsNow repo:VSSF                             |  'QueueJobsNow' inside repositories named 'VSSF'                 |
| Ext           | QueueJobsNow ext:cs                                 | 'QueueJobsNow' with file extension as .cs                        |
|     Path      |  QueueJobsNow path:VisualStudio/Services/Framework  |  'QueueJobsNow' under the path 'VisualStudio/Services/Framework' |

### Code Type filters
Filter your search results to find results with query words mapped to a code type 

|   Example search   |                    Finds code containing...                   |
|:------------------:|:-------------------------------------------------------------:|
|    arg:foo         |  'foo' where it appears as a argument                         |
|    basetype:foo    |  'foo' where it appears as a basetype                         |
|    class:foo       |  'foo' where it appears as a class definition or declaration  |
|    classdecl:foo   |  'foo' where it appears as a class declaration                |
|    classdef:foo    |  'foo' where it appears as a class definition                 |
|    comment:foo     |  'foo' where it appears as a comment                          |
|    ctor:foo        |  'foo' where it appears as a constructor                      |
|    decl:foo        |  'foo' where it appears as a declaration                      |
|    def:foo         |  'foo' where it appears as a definition                       |
|    dtor:foo        |  'foo' where it appears as a destructor                       |
|    enum:foo        |  'foo' where it appears as an enumerator                      |
|    extern:foo      |  'foo' where it appears as an extern                          |
|    field:foo       |  'foo' where it appears as a field                            |
|    friend:foo      |  'foo' where it appears as a friend function                  |
|    func:foo        |  'foo' where it appears as a function                         |
|    funcdecl:foo    |  'foo' where it appears as a function declaration             |
|    funcdef:foo     |  'foo' where it appears as a function definition              |
|    global:foo      |  'foo' where it appears as a global                           |
|    header:foo      |  'foo' where it appears as a header                           |
|    interface:foo   |  'foo' where it appears as a interface                        |
|    macro:foo       |  'foo' where it appears as a macro                            |
|    macrodef:foo    |  'foo' where it appears as a macro definition                 |
|    macroref:foo    |  'foo' where it appears as a macro reference                  |
|    method:foo      |  'foo' where it appears as a method                           |
|    methoddecl:foo  |  'foo' where it appears as a method declaration               |
|    methoddef:foo   |  'foo' where it appears as a method definition                |
|    namespace:foo   |  'foo' where it appears as a namespace                        |
|    prop:foo        |  'foo' where it appears as a property                         |
|    ref:foo         |  'foo' where it appears as a reference                        |
|    strlit:foo      |  'foo' where it appears as a string literal                   |
|    struct:foo      |  'foo' where it appears as a struct                           |
|    structdecl:foo  |  'foo' where it appears as a struct declaration               |
|    structdef:foo   |  'foo' where it appears as a struct definition                |
|    tmplarg:foo     |  'foo' where it appears as a template argument                |
|    tmplspec:foo    |  'foo' where it appears as a template specification           |
|    type:foo        |  'foo' where it appears as a type                             |
|    typedef:foo     |  'foo' where it appears as a typedef                          |
|    union:foo       |  'foo' where it appears as a union                            |

### Phrase Search
Enclose your search string within quotes to find an exact word or set of words. This is helpful when searching for error logs or a sentence in comments. It's also useful in specifying paths containing spaces. 

| Example search                                           |  Finds code containing...                                             |
|----------------------------------------------------------|-----------------------------------------------------------------------|
|     "Client not found"                                   |  the exact phrase "Client not found"                                  |
|    WorkItemHandler path:"Microsoft\Windows Phone\Blue\"  |  word 'WorkItemHandler' under the path "Microsoft\Windows Phone\Blue" |

### Wildcard Search
Use \* as part of the search text to return results containing exact matches of the search text, as well as results that contains the search string and any number of other characters in place of  \*. It may be used in the start, middle or end of the string. Using ? in a search string returns only results that contain the search string with one additional character in place of ?. Wildcard * is helpful when you remember one of the folder/file names of the path you want to search in but not the complete tree. 

| Example search                    |  Finds code containing...                                                                                       |
|-----------------------------------|-----------------------------------------------------------------------------------------------------------------|
|     CodeSensehttp*                |  words beginning with CodeSensehttp Eg: CodeSensehttpclient, CodeSensehttpclienttest, etc.                      |
|  CSharp Parser AND path:*search*  |  both words 'CSharp' and 'Parser' and under a path containing 'search'                                          |
|            git *httpclient        |  words 'git' as well as atleast one word ending with httpclient Eg: CodeSensehttpclient, SetupHttpClient, etc.  |
|     Error code 40?                |  words 'Error', 'code' and three letter words starting with '40' i.e, any number from 400 to 409.               |

### Operators
Narrow down or expand your search results by creating logical expressions using operators. By default, words in a search are combined with an AND operator. Query parts can be grouped to operate as a single unit separate from the rest of the query by putting parentheses around an expression like in a mathematical equation or logic statement. The following operators are supported: 

|      Operator       |           Example search          |  Finds code containing...                               |
|:-------------------:|:---------------------------------:|---------------------------------------------------------|
|         AND         |          TODO AND revisit         |  Both words 'TODO' as well as 'revisit'                 |
|          OR         |          TODO OR revisit          |  Either word 'TODO' or 'revisit'                        |
|         NOT         |          TODO NOT revisit         |  Word 'TODO' but not 'revisit'                          |
|     Parentheses     |  (TODO OR revisit) AND hardcoded  |  Words 'TODO' or 'revisit', as well as word 'hardcoded' |

**Note:** AND, OR and NOT behave as operators when typed in upper case and as query words in lower case. 

## Filters 
Narrow down your results by applying project, repository or code type filters. Selecting multiple filters results in an OR operation across filters. No filter selection under a category implies no filters are applied. The filters are divided into three categories: 

### Search for
This lists down the various visual studio entities Eg: code, project, etc. that your results span across. Currently only code type search is supported. 

### Search in
Narrow down your results to a particular project or projects. To search across projects, you may reset the 'Search In' filter or uncheck all the project filters. By selecting only one project you also get an option to scope your results to a set of repositories inside the project. 

### Refine by
Filter your search results to find results with query words mapped to a code type. 

## Contact Us
We would love to hear your feedback, suggestions and requests. Feel free to drop a mail to almsearchfeedback@microsoft.com with your ideas. 


