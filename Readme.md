Raku Templates
=================
XCode templates for Raku.

To install them, copy the content of the code/Raku folder into ~/Library/Developer/Xcode/Templates/Project Templates/Raku.

The content of code/tools must be in ~/.raku/tools.

In the downloads section you can find an installer that automates this process.

Instructions
____________
To create a project with the templates, first create a layout with the following structure:

- Project
	- code
	- docs
	
The project must be placed inside the code folder.

Once the project is created, inside the root (Project folder in this example) execute the following git commands:

- git init
- git add *.gitignore
- git add *

Then, inside the code/Project folder execute

`rake ios:setup_dependencies`

This command will download the dependencies into the Libraries folder. Drag and Drop the folders into the project in Xcode, in the folder "Frameworks".

BlocksKit and CocoaLumberjackNSLogger must be added into the project and Tests targets.
GHUnit only into the Tests target.

run `rake --tasks` to see the available taks.

Rake Tasks
__________

- ios:documentation
Runs appledoc and generates the projects documentation in the folder Project/docs/Code/appledoc

- ios:clean
Cleans the project and deletes the build dir

- ios:analyze
Runs Clang static analyze and generates a report if it found any error. The report is placed in Project/docs/Code/static_analysis

- ios:compile
Compiles the project in Debug Scheme. The .app is placed in the build dir.

- ios:release
Compiles the project in Release Scheme. The .app is placed in the build dir.

- ios:run
Runs the app compiled in Debug mode in the simulator.

- ios:run_tests
Compiles the Tests target, runs it in the Simulator and store the results in the Project/docs/Code/tests_results

	

__________________
&copy;Raku 2011