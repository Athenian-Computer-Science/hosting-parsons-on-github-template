---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: Multiple Parson's Problems on One Page
---
# Parsons Practice

## Parsons 1 (Line Based Grader)
Re-arrange the blocks below so they print out "Hello World!"

<div id="p1-sortableTrash" class="sortable-code"></div>
<div id="p1-sortable" class="sortable-code"></div>
<div style="clear:both;"></div>
<p>
    <input id="p1-feedbackLink" value="Get Feedback" type="button" />
    <input id="p1-newInstanceLink" value="Reset Problem" type="button" />
</p>
<script type="text/javascript">
(function() {
  var initial = "print(\"Hello\")\n" +
    "print(\" \")\n" +
    "print(\"World\")\n" +
    "print(\"!\")";
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "p1-sortable",
    "max_wrong_lines": 10,
    "grader": ParsonsWidget._graders.LineBasedGrader,
    "exec_limit": 2500,
    "can_indent": false,
    "x_indent": 50,
    "lang": "en",
    "trashId": "p1-sortableTrash"
  });
  parsonsPuzzle.init(initial);
  parsonsPuzzle.shuffleLines();
  $("#p1-newInstanceLink").click(function(event){
      event.preventDefault();
      parsonsPuzzle.shuffleLines();
  });
  $("#p1-feedbackLink").click(function(event){
      event.preventDefault();
      parsonsPuzzle.getFeedback();
  });
})();
</script>


## Parsons 2 (Variable Check Grader)
Construct a program that swaps the values of variables <code>x</code> and <code>y</code> using the helper variable <code>tmp</code>. You can change the names of the variables (<span class="jsparson-toggle"></span>) by clicking them.

<div id="p2-sortableTrash" class="sortable-code"></div>
<div id="p2-sortable" class="sortable-code"></div>
<div style="clear:both;"></div>
<p>
    <input id="p2-feedbackLink" value="Get Feedback" type="button" />
    <input id="p2-newInstanceLink" value="Reset Problem" type="button" />
</p>
<script type="text/javascript">
(function(){
  var initial = "$$toggle::x::y::tmp$$ = $$toggle::x::y::tmp$$\n" +
    "$$toggle::x::y::tmp$$ = $$toggle::x::y::tmp$$\n" +
    "$$toggle::x::y::tmp$$ = $$toggle::x::y::tmp$$";
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "p2-sortable",
    "max_wrong_lines": 10,
    "grader": ParsonsWidget._graders.VariableCheckGrader,
    "exec_limit": 2500,
    "can_indent": true,
    "x_indent": 50,
    "lang": "en",
    "trashId": "p2-sortableTrash",
    "vartests": [
        {
            "message": "Testing with initial variable values x = 3 and y = 4",
            "initcode": "x = 3\ny = 4",
            "code": "",
            "variables": {}
        },
        {
            "message": "Testing with initial variable values x = 0 and y = 2",
            "initcode": "x = 0\ny = 2",
            "code": "",
            "variables": {}
        }
    ]
  });
  parsonsPuzzle.init(initial);
  parsonsPuzzle.shuffleLines();
  $("#p2-newInstanceLink").click(function(event){
      event.preventDefault();
      parsonsPuzzle.shuffleLines();
  });
  $("#p2-feedbackLink").click(function(event){
      event.preventDefault();
      parsonsPuzzle.getFeedback();
 });
})();
</script>

## Parsons 3 (Unit Test Grader)
Your task is to construct a function which returns the index of the largest element in the array.

<div id="p3-sortableTrash" class="sortable-code"></div>
<div id="p3-sortable" class="sortable-code"></div>
<div style="clear:both;"></div>
<p>
    <input id="p3-feedbackLink" value="Get Feedback" type="button" />
    <input id="p3-newInstanceLink" value="Reset Problem" type="button" />
</p>
<script type="text/javascript">
(function(){
  var initial = "def maxindex(arg):\n" +
    " ans = 0\n" +
    " for i in range(len(arg)):\n" +
    " if arg[i] > arg[ans]:\n" +
    " ans = i\n" +
    " while True:\n" +
    "pass\n" +
    " return ans";
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "p3-sortable",
    "max_wrong_lines": 10,
    "grader": ParsonsWidget._graders.UnitTestGrader,
    "exec_limit": 2500,
    "can_indent": true,
    "x_indent": 50,
    "lang": "en",
    "trashId": "p3-sortableTrash",
    "unittests": "import unittestparson\nclass myTests(unittestparson.unittest):\n  def test_0(self):\n    self.assertEqual(,,)\n_test_result = myTests().main()"
  });
  parsonsPuzzle.init(initial);
  parsonsPuzzle.shuffleLines();
  $("#p3-newInstanceLink").click(function(event){
      event.preventDefault();
      parsonsPuzzle.shuffleLines();
  });
  $("#p3-feedbackLink").click(function(event){
      event.preventDefault();
      parsonsPuzzle.getFeedback();
  });
})();
</script>

## Parsons 4 (Language Translation Grader)
Print out "I am a Java program" three times using a for loop.

<div id="p4-sortableTrash" class="sortable-code"></div>
<div id="p4-sortable" class="sortable-code"></div>
<div style="clear:both;"></div>
<p>
    <input id="p4-feedbackLink" value="Get Feedback" type="button" />
    <input id="p4-newInstanceLink" value="Reset Problem" type="button" />
</p>
<script type="text/javascript">
(function(){
  var initial = "for (int i=0;i<3;i++) {\n" +
    "System.out.print(\\\"I \\\");\n" +
    "System.out.print(\\\"am \\\");\n" +
    "System.out.print(\\\"a Java program \\\");\n" +
    "}";
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "p4-sortable",
    "max_wrong_lines": 1,
    "grader": ParsonsWidget._graders.LanguageTranslationGrader,
    "exec_limit": 2500,
    "can_indent": true,
    "x_indent": 50,
    "lang": "en",
    "executable_code": "for x in range(3):\n    output += 'I '\n    output += 'am '\n    output += 'a Java program '\npass",
    "programmingLang": "java",
    "vartests": [
        {
            "message": "Testing...",
            "initcode": "output = ''",
            "code": "",
            "variables": {
                "output": "I am a Java program I am a Java program I am a Java program "
            }
        }
    ]
  });
  parsonsPuzzle.init(initial);
  parsonsPuzzle.shuffleLines();
  $("#p4-newInstanceLink").click(function(event){
      event.preventDefault();
      parsonsPuzzle.shuffleLines();
  });
  $("#p4-feedbackLink").click(function(event){
      event.preventDefault();
      parsonsPuzzle.getFeedback();
   });
})();
</script>


## Parsons 5 (Turtle Grader)
Construct a program by dragging&amp;dropping and reordering lines. The constructed program should draw a triangle like shown below.

<div id="p5-sortableTrash" class="sortable-code"></div>
<div id="p5-sortable" class="sortable-code"></div>
<div style="clear:both;"></div>
<p>
    <input id="p5-feedbackLink" value="Get Feedback" type="button" />
    <input id="p5-newInstanceLink" value="Reset Problem" type="button" />
</p>
<script type="text/javascript">
(function(){
  var initial = "REPEAT 3 TIMES\n" +
    "  forward(100)\n" +
    "  left(120)\n" +
    "ENDREPEAT";
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "p5-sortable",
    "max_wrong_lines": 1,
    "grader": ParsonsWidget._graders.TurtleGrader,
    "exec_limit": 2500,
    "can_indent": true,
    "x_indent": 50,
    "lang": "en",
    "trashId": "p5-sortableTrash",
    "executable_code": "for i in range(0,3):\nmyTurtle.forward(100)\nmyTurtle.left(120)\npass",
    "programmingLang": "pseudo",
    "turtleModelCode": "modelTurtle.forward(100)\nmodelTurtle.left(120)\nmodelTurtle.forward(100)\nmodelTurtle.left(120)\nmodelTurtle.forward(100)\nmodelTurtle.left(120)",
  });
  parsonsPuzzle.init(initial);
  parsonsPuzzle.shuffleLines();
  $("#p5-newInstanceLink").click(function(event){
      event.preventDefault();
      parsonsPuzzle.shuffleLines();
  });
  $("#p5-feedbackLink").click(function(event){
      event.preventDefault();
      parsonsPuzzle.getFeedback();
  });
})();
</script>

### Implementation Notes

When you host multiple Parson's problems on a single markdown page, you need to add a unique prefix. You can easily do this in the Codio generator by typing a unique prefix into the "Prefix" textbox and pressing Enter/Return. Then you can simply copy-paste like normal.

If want each problem to be it's own page, you can use relative path links at the bottom of each of your markdown pages as seen below. If you want students to be able to return to previous problems in this format, consider adding previous links or link to a table of contents like page.

### Example Next Link
[Next](./parsons/example1.html)

### Parsons 6 (ML)
<div id="for1-sortableTrash" class="sortable-code"></div> 
<div id="for1-sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="for1-feedbackLink" value="Get Feedback" type="button" /> 
    <input id="for1-newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "for i in range(3):\n" +
    "  if i == 1:\n" +
    "    print(&quot;odd&quot;)\n" +
    "  else:\n" +
    "    print(&quot;even&quot;)\n" +
    "else goal &lt; 10: #distractor\n" +
    "for i in range(4): #distractor\n" +
    "if i == 5: #distractor";
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "for1-sortable",
    "max_wrong_lines": 1,
    "grader": ParsonsWidget._graders.LineBasedGrader,
    "exec_limit": 2500,
    "can_indent": true,
    "x_indent": 50,
    "lang": "en",
    "trashId": "for1-sortableTrash"
  });
  parsonsPuzzle.init(initial);
  parsonsPuzzle.shuffleLines();
  $("#for1-newInstanceLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.shuffleLines(); 
  }); 
  $("#for1-feedbackLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.getFeedback(); 
  }); 
})(); 
</script>

### 1.2 printing
<div id="hello_world-sortableTrash" class="sortable-code"></div> 
<div id="hello_world-sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="hello_world-feedbackLink" value="Get Feedback" type="button" /> 
    <input id="hello_world-newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "course = &#039;Chemistry&#039;\n" +
    "print(f&quot;What class comes after {course}?&quot;)\n" +
    "course = Chemistry #distractor\n" +
    "&#039;Chemistry&#039; = course #distractor\n" +
    "print(&quot;What class comes after {course}?&quot;) #distractor\n" +
    "print f&#039;What class comes after {course}?&#039; #distractor";
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "hello_world-sortable",
    "max_wrong_lines": 10,
    "grader": ParsonsWidget._graders.LineBasedGrader,
    "exec_limit": 2500,
    "can_indent": false,
    "x_indent": 50,
    "lang": "en",
    "trashId": "hello_world-sortableTrash"
  });
  parsonsPuzzle.init(initial);
  parsonsPuzzle.shuffleLines();
  $("#hello_world-newInstanceLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.shuffleLines(); 
  }); 
  $("#hello_world-feedbackLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.getFeedback(); 
  }); 
})(); 
</script>

### 1.3 input and print
<div id="input_print-sortableTrash" class="sortable-code"></div> 
<div id="input_print-sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="input_print-feedbackLink" value="Get Feedback" type="button" /> 
    <input id="input_print-newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "name = input(&#039;Please enter your name: &#039;)\n" +
    "print(f&quot;Welcome, {name}!&quot;)\n" +
    "name = print(&#039;Please enter your name:                 &#039;) #distractor\n" +
    "name = print(input(&#039;Please enter your name: &#039;)) #distractor\n" +
    "print(f&#039;It&#039;s nice to meet you, {name}!&#039;) #distractor\n" +
    "print(&quot;It&#039;s nice to meet you, {name}!&quot;) #distractor\n" +
    "print(f&quot;It&#039;s nice to meet you, name!&quot;) #distractor";
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "input_print-sortable",
    "max_wrong_lines": 10,
    "grader": ParsonsWidget._graders.LineBasedGrader,
    "exec_limit": 2500,
    "can_indent": true,
    "x_indent": 50,
    "lang": "en",
    "trashId": "input_print-sortableTrash"
  });
  parsonsPuzzle.init(initial);
  parsonsPuzzle.shuffleLines();
  $("#input_print-newInstanceLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.shuffleLines(); 
  }); 
  $("#input_print-feedbackLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.getFeedback(); 
  }); 
})(); 
</script>

### Input/print 2
      
<div id="sortableTrash" class="sortable-code"></div> 
<div id="sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="feedbackLink" value="Get Feedback" type="button" /> 
    <input id="newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "name = input(&quot;What is your name? &quot;)\n" +
    "print(f&quot;Welcome to CS, {name}!&quot;)\n" +
    "print(f&quot;Welcome to CS, name!&quot;) #distractor\n" +
    "print(&quot;Welcome to CS, {name}!&quot;) #distractor\n" +
    "name = print(input(&quot;What is your name? &quot;)) #distractor";
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "sortable",
    "max_wrong_lines": 10,
    "grader": ParsonsWidget._graders.LineBasedGrader,
    "exec_limit": 2500,
    "can_indent": false,
    "x_indent": 50,
    "lang": "en",
    "trashId": "sortableTrash"
  });
  parsonsPuzzle.init(initial);
  parsonsPuzzle.shuffleLines();
  $("#newInstanceLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.shuffleLines(); 
  }); 
  $("#feedbackLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.getFeedback(); 
  }); 
})(); 
</script>


      
CS Parsons problems:
* [print](parsons/print.md)
* [input & print](parsons/input-print.md)
* [variable reassignment](parsons/variable-reassignment.md)
* [basic functions 1](parsons/basic-function-1.md)
* [basic functions 2](parsons/basic-function-2.md)
* [functions - return multiple values](parsons/return-multiple-values.md)
* [If Statements](parsons/if-elif-else.md)
* [For Loops 1](parsons/for_loops_1.md)
* [Lists 1](parsons/lists1.md)
* [List slicing](parsons/list_slicing.md)
* [Lists - check contents](parsons/lists-check-contents.md)

Embed Repl:
embed = true
<iframe frameborder="0" width="100%" height="500px" src="https://replit.com/@MeganLeich/testrepl?embed=true"></iframe>

embed - lite
<iframe frameborder="0" width="100%" height="500px" src="https://replit.com/@MeganLeich/testrepl?lite=true"></iframe>

embed different repl
<iframe frameborder="0" width="100%" height="500px" src="https://replit.com/@MeganLeich/testembed?embed=true"></iframe>

