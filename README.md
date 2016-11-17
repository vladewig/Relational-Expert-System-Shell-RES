# Relational Expert System Shell - RES
#**Ideas for a Relational Expert System Shell (RES) - copyright 1992, 2016 Dr Vince Ladewig**
The initial idea for the RES grew from a desire to create an expert system shell back in 1992 for use in building an expert system for determining the "site of lesion" from information obtained from performing a battery of audiometric tests:  
  + PTA - air and bone  
  + Tympanometry  
  + Impedance  
  + Reflex  
  + Speech  
  + Auditory Brainstem Evoked Responses (ABER)  
  
##**The RES as first developed**
The RES consisted of three databases - the Problem Definition, Problem Space and Run Enquiry databases.  The Problem Definition data base was populated by the user during problem definition.  The Problem Space was populated by the system once the problem had been defined.  The Run Enquiry data base was a collection of logs generated as a user traversed the problem network in order to answer/solve a problem.  
###**Problem Definition**
The problem Definition database holds the definitions of the problems, their inputs, the values that inputs may take and the possible results of a problem.  
This database maintains the network of problems. The problem network is an interlinking structure of problems. The linking is via  subproblem inputs and problem flow results - backward and forward chaining.   
A problem might be a main problem, subproblem or a flow problem.  
A problem has inputs.  
Inputs take on allowed values.  
The RES allows for backward chaining - an input to a problem may also be the result obtained from a subproblem. 
A problem has results.  
Results take on allowed values.  
A result might be an answer and is the endpoint of the problem network.
A result might flow into another problem (a flow problem result) - forward chaining
A result might be a subproblem result and this result provides an input value for another problem.  
The RES allowed for the assignment of a result to each unique combination of input values - see Problem Space below.
The result was chosen from allowed values.
The RES allowed for refining the granularity of the problem web/network.  
Various checks are made as the problems are defined to ensure the integrity of the problem definitions.  
####**Problems**


####**Inputs**


####**Results**


###**Problem Space**
The RES generates the Problem Space for each problem in the problem network.  
A problem space of a problem is the database generated from all combinations of the values of all inputs for a problem.  
An interface is provided to allow the expert to assign a result to each row in the generated problem space table.  
Various checks are made to ensure integrity of the problem spaces.   

###**Run Enquiry**
A mechanism exists for traversing the network of problems.  
A traverse of a problem network is captured in a log.  
The depth of backward chaining could become an issue when traversing - i.e. using - the expert system so developed.  The depth was limited by the amount of system memory available to the process.  
During the traverse a record is kept of the problem spaces visited, the values of inputs used and the results obtained.  
A traverse is commenced at the main problem and input questions are asked in alphabetic order.  


##**Some History**
The initial published RES system (Version 2.0MU circa 1992) was built in DOS using a product called DataBoss (Kedwell Software - Brisbane OZ based).  
DataBoss was a flexible development environment which used TurboPascal (Borland) as the language for building relational database management systems.  
DataBoss provided the generic code for managing the housekeeping (add, edit, delete etc) after the developer entered the table definitions, keys and uniqueness constraints as well as field types and constraints.  
DataBoss allowed the developer to insert TurboPascal code into the "skeleton" files used by DataBoss to generate the source code for each user defined data base.
The generated source code was then compiled.  

##**Present Plan**
The present plan (October 2016) is to revist the initial definitions (NIAM entity relationship model) upon which the RES is based and build a RES in C++ or C# in Visual Studio.  No decision has been made as to which data base management system the RES will be defined in.  The intention is to develop a graphic interface using "R" and the "igraph" package to display a problem network.  
mySQL may be the initial database used for defining the updated RES which is then used to store a the problems.  
It is likely that initially an expert system suitable for testing the ideas in R may need to be bootstrapped from predefined tables (data frames) built by hand to reflect what would normally, in production, be available from reading the particular RES expert system built in mySQL.  
Refinements will need to cater for contiuously variable input values.  Also the result of a problem may need to be a calculated result for example eGFR.  
It would be useful for the inputs to a problem to be determined in the most logically efficient way - not just in alphabetic order. This could be achieved by weighting inputs by their impact on the result. It should be possible to move to a result for a problem as soon as sufficient questions/inputs have been qualified to give a unique result for the problem. Only need to ask for as many input values as needed for a unique result.  
Links would be useful to local or external resources to help the user of the expert system in understanding the concepts being interrogated by the input questions, the problem being explored and results obtained - this would allow the expert system to be deployed as a teaching tool.  

##**Preparing your Data for the RES**
It is worthwhile spending time preparing the problem network on paper - large sheets of butcher's paper are ideal.  
Do not be too concerned with what inputs to a problem lead to which outputs/results/answers.  
Do not get bogged down in too fine an analysis in the first iteration - remeber that you can change the granularity of the problem network/web later.  
I use a circle to represent a problem - give it a unique name.  
Inputs are the questions to be asked when solving a problem - each input will have a number of values that they can take.
Draw inputs as lines into a problem. Place an arrow on the end of the line as it touches the problem circle to indicate direction to the problem. Write the name of the input beside the line and list the valid values the input can take near the line.  
A problem can have a number of results - a result may be an answer - draw a line from the problem circle to a box with the answer in it. Use an arrow on the end of the line as it touches the box to indicate direction from the problem to the answer.
More usually a problem may be an intermediate problem and the result will direct the user to another problem - this is a flow problem result. Draw this as a line from the original problem circle into the centre of the other problem circle - place an arrow on the end of the line to indicate diretion.  
A problem might need to have another problem solved ( a subproblem) before a result is able to be obtained. Draw this as a line from the subproblem to the problem of interest with an arrow on the end of the line as it touches the problem of interest.  

Initially aim to get a broad usable model of the knowledge domain into the RES.  
Test this simple model.  
Reine the granularity for example some inputs may become subproblem inputs or split some problems into two or more problems with results flowing into another problem.  
