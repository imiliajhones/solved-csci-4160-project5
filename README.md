Download Link: https://assignmentchef.com/product/solved-csci-4160-project5
<br>
<strong>Description: </strong>

This is a team project that build on the previous project. In this project, you are required to implement a symbol table, and perform every basic semantic error checking listed below:  undefined type/variable/function names  redefined type/variable names.

All other semantic errors will not be covered in this project.




<strong>Classes in this project </strong>

Several classes are defined in different namespace for various purposes. Here is a short explanation of each class.

<ul>

 <li>Class absyn::Absyn and all its children are used to define types of nodes in the abstract syntax tree.</li>

 <li>Class template symbol::SymbolTable provides the implementation of symbol tables used in this course.</li>

 <li>Class types::Type and all its children are used to represent types supported by tiger languages. We are not going to use them in this project. But we need them to make sure the syntax is correct, and no change is needed for the next project.</li>

 <li>Structure symbol::SymTabEntry provides information that should be tied with a variable/function/type name in the SymbolTable. The SymTabEntry contains three information: the level of associated name in the source program, a pointer to the type information of the name, and a pointer to the AST node that contains the variable/function/type.</li>

 <li>Class symbol::Env provides the compile environment for Tiger language. It has two member data of symbol::SymbolTable&lt;SymTabEntry&gt;, one to store variable/function information, and one to store type information as specified by Tiger language manual. Its constructor will insert all global functions like print, ord into variable symbol table, and built-in data types like int, and string into type symbol table.</li>

 <li>Class semantics::TypeChecking provides functions to check semantic errors at each node in the abstract syntax tree..</li>

</ul>




Your major task is to complete the implementation of the following classes.

<ul>

 <li>SymbolTable: this class define a class template for symbol table</li>

 <li>TypeChecking: this class performs the basic type checking using the symbol table You should not modify other classes in the project.</li>

</ul>




<strong>Tips: </strong>

<ol>

 <li>tab.hh, Tiger.tab.cc, lex.yy.cc files are provided by instructor in SymbolTableProject. So you don’t need to use your own tiger.ll or tiger.yy files in this project. When you compile the solution, please just build the MainDriver project.</li>

</ol>




<ol start="2">

 <li>Every time an item is inserted into the variable or type symbol table, a SymTabEntry object should be construct. In this project, please pass NULL to the second parameter when constructing a SymTabObject. Let d be a pointer to an absyn::VarDec object, the following statement will insert it into the variable symbol table:</li>

</ol>

<strong>     insertVar( d-&gt;getName(),  </strong>

<strong>symbol::SymTabEntry( </strong>

<strong>                    env.getVarEnv()-&gt;getLevel(), </strong>

<strong>                    NULL,                  d)  </strong>

<strong>); </strong>

where insertVar function is provided in the class semantics::TypeChecking




<strong>Test Report: </strong>

In this project, implementation of the project and test case design can be performed simultaneously. Don’t wait too long to design test cases. In this project, please provide a tiger program called: test.tig to cover all of the following scenarios:

<ul>

 <li>Two variables with the same name are defined at the same level.</li>

 <li>Two types with the same name are defined at the same level.</li>

 <li>Two functions with the same name are defined at the same level.</li>

 <li>One variable and one function with the same name are defined at the same level.</li>

</ul>




<ul>

 <li>Two variable with the same name are defined at the different nesting levels.</li>

 <li>Two types with the same name are defined at the different nesting levels.</li>

 <li>Two functions with the same name are defined at the different nesting levels.</li>

 <li>One variable and one function with the same name are defined at the different nesting levels.</li>

</ul>




<ul>

 <li>An undefined variable is used</li>

 <li>An undefined type is used</li>

 <li>An undefined variable is used in function parameter list</li>

 <li>An undefined function is used</li>

</ul>




<strong>Instructor provided files in the class repository </strong>




The following files are provided by the instructor:

<ul>

 <li>SymbolTableProject folder. This contains a sample Visual Studio 2010 project.</li>

 <li>pdf: this file</li>

 <li>doc: the rubric used to grade this assignment.</li>

 <li>txt. sample output</li>

 <li>doc: format of testing report for this project</li>

</ul>





