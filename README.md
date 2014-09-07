A basic kjar template with CEP, JUnit 4 and Eclipse org.eclipse.m2e lifecycle-mapping plug-in settings.

## Installation

Clone this git project and Eclipse > Import as "Existing Maven project".

Right click on project in workspace, Run As > Maven install.

## Usage

Create new Maven Project in Eclipse, the archetype will be available in the catalog.

## Background

I found myself creating many times a single-use, disposable, simple template project for testing new rules or new concepts in isolation.

However the creation of this kind of project in Eclipse, usually required performing manually the following steps:
* Create new Maven project with archetype quickstart
* Set-up the new project's pom:
  * Change Java version to 1.6 or greater, by including the maven-compiler-plugin
  * Add Drools dependencies
  * Change JUnit dependencies to version 4
  * Add kie-maven-plugin
  * Add plug-in org.eclipse.m2e/lifecycle-mapping settings, to avoid Eclipse ERROR at the pom.xml line defining the kie-maven-plugin
  * Set packaging to 'kjar'
* Creation of an initial .drl file in src/main/resources 
* Creation of minimal kmodule.xml in src/main/resources/META-INF directory
* Create a simple JUnit test for:
  * Creation of KieBase with STREAM option for CEP features
  * Creation of KieSession with pseudo-clock
  * Advance / Insert / Fire template
  * ... and other verification/output patterns
* Include SLF4J and LOG4J binding for logging, including a log4j.properties file in src/test/resources

This archetype automate the above steps.