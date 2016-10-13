# hello-world
##**Ideas for a Relational Expert System (RES) - copyright 1992, 2016 Vince Ladewig**
The initial idea for the RES grew from a desire to create an expert system shell back in 1992 for use in building a expert system for determining the "site of lesion" from information obtained from performing a battery of audiometric tests:  
  + PTA - air and bone  
  + Tympanometry  
  + Impedance  
  + Reflex  
  + Speech  
  + Auditory Brainstem Evoked Responses (ABER)  
  
##**The RES as first developed**
  A problem might be a main problem or a subproblem  
  A problem has inputs which take on allowed values    
  A problem space is the table generated from all combinations of values of all inputs for a problem  
  A problem has results  
  A result might be an answer or flow into another problem  
  Each row in the generated problem space table is assigned a result by the expert  
  Various checks are made to ensure integrity of the problems and problem spaces  
  A mechanism exists for traversing the web of problems  
  During the traverse a record is kept of the problem spaces visited, the values of inputs used and the results obtained  
  An input might be the result from a problem  
  The RES allows for backward chaining - the depth was determined by the amount of memory  
  A traverse of a problem web is captured in a log  
  The RES allows for refining the granularity of the web of problems  

##**Some History**
The initial published RES system (Version 2.0MU circa 1992) was built in DOS using a product called DataBoss (Kedwell Software - Brisbane OZ based).  
DataBoss was a flexible development environment which used TurboPascal (Borland) as the language for building relational database management systems.  
DataBoss provided the generic code for managing the housekeeping (add, edit, delete etc) after the developer entered the table definitions, keys and uniqueness constraints as well as field types and constraints.  
DataBoss allowed the developer to insert TurboPascal code into the "skeleton" files used by DataBoss to generate the source code for each user defined data base.
The generated source code was then compiled.  

##**Present Plan**
The present plan (October 2016) is to revist the initial definitions (NIAM entity relationship model) upon which the RES is based and use these ideas to develop a graphic interface using "R" and the "igraph" package.  
mySQL may be the initial database used for defing the updated RES which is then read to build the web of problems.  
It is likely that initially an expert system suitable for testing the ideas in R may need to be bootstrapped from predefined tables (data frames) built by hand to reflect what would available from reading a RES built in mySQL.    

##**Preparing your Data for the RES**
It is worthwhile spending time preparing the problem network on paper - large sheets of butcher's paper are ideal.  
Do not be too concerned with what inputs to a problem lead to which outputs/results/answers.  
Do not get bogged down in too fine an analysis in the first iteration - remeber that you can change the granularity of the problem network/web later.  
I use a circle to represent a problem - give it a unique name.  
Inputs are the questions to be asked when solving a problem - each input will have a number of values that they can take.
Draw inputs as lines into a problem. Place an arrow on the end of the line as it touches the problem circle to indicate direction to the problem. Write the name of the input beside the line and list the valid values the input can take near the line.  
A problem can have a number of results - a result may be an answer - draw a line from the problem circle to a box with the answer in it. Use an arrow on the end of the line as it touches the box to indicate direction from the problem to the answer.
More usually a problem may be an intermediate problem and the result will direct the user to another problem - this is a flow problem result. Draw this as a line from the original problem circle into the centre of the other problem circle - place an arrow on the end of the line to indicate diretion.  
A problem might need to have another (sub)problem solved before a result is able to be obtained. Draw this as a line from the subproblem to the problem of interest with an arrow on the end of the line as it touches the problem of interest.  
