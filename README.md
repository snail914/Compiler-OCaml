This repo is created for a school project.

To run and test the compiler :  ocamlbuild Main.byte -- tests/Test_fonction.mjava

Project structure : 
1. Typer: ( complete)
  1.1  Typing/Env.ml 
  This file creates the typing environment, which contains two environments: 
   env_cl ->  used to store and type class, methods and attributes of class
   env_vl -> used to store and type local variable. env_cl is refreshed each time when a method is called
  
  1.2  Typing/Typer.ml
  This file typies an AST tree step by step, firstly add class name to Env.ml, then 
  set class parent, then type attributes and finally type methods of the class
  
  1.3 Typing/ExprTyper.ml
  This file is a part of Typer.ml, which focuses on typing expressions (give type to expression)

2. Compilation ( complete)
  2.1 Compiling/EnvHeap.ml
  This file creates a virtual heap(tas) to store all class informations. Since the type is already testet in typer part,
  we ignore the type of each varaible. 
  To store an attribute, we use its name, its belonging class name and its expression_desc.
  To store a method, we use its name, its belonging class name, its inside expression, 
  and its arguments' name (name's value will replace variable in body expression) 
  2.2 Compiling/Compilation.ml
  Add all classes and its attributes and methods to EnvHeap.ml
  
3. Evaluation (Basic Functions)
  Our Evaluation part is not completely finished, for instance, it can only evaluate regular expresions with Int, String and Boolean type,
  which means it can't evaluate expressions inside a class method.


