# UiPath AutomationTestRobot
Without any more coding, you can automate testing your UiPath projects. This project enables test driven development in UiPath.

## Inspiration
Testing in UiPath was horrible as you have to manually edit your (in/out) arguments every time, then click RUN button.
While most of programing languages provide testing frameworks and CICD approach, workflow-style UiPath codes are lacking of these.
My objective is to qualify UiPath codes by enabling automated tests and CICD approach.

## What it does
* 1. Automate generating test-case (template in excel) for each .xaml file, so you can input your test data (with In/Out arguments). All you do in excel.
* 2. Automate running all your test cases and reporting results
* 3. You can choose test only 1 case, or all cases at once.
* 4. Generate its own log files (besides UiPath Robot log), for furthur analyzing test result in CICD in the future version.
* 5. Build your CICD by running the AutomationTestRobot as unattended for automating testing your continuous UiPath development.

## How I built it 
I wrote the Automation Test Robot just by UiPath only, without external library. So it is compatible with any environment, and easy to execute. Run it in your studio, or publish it as robot.

## Challenges I ran into
* 1. UiPath .xaml file invoke codes by relative path in its projects (not relative path of the two files). So, in the beginning, I was just able to test no-invoke-other-workflow file. TODO: Able to test nested-invoke-workflow files.
* 2. Check coding standards is quite challenging in .xaml workflow. Some basic rules may be: no generic-value type, variable names rules, maximum numbers of out arguments, etc. More complicated rules are no too-much-nested sequences, independent in business logic workflow, etc. Noted: not yet implement this challenge.

## What's next for Automation Test Robot
* 1. TODO: scan UiPath codes (.xaml) to check coding standards
* 2. TODO: support nested-invoked workflow files
* 3. TODO: resolve dependences (between workflows, like: workflow A must run before workflow B)
