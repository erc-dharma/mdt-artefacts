# mdt-artefacts
DHARMA Artefacts metadata

CSV folder = strong the csv files for artefacts and conglomerate artefacts of the projects downloaded from googleSheets. 
output = temporary files for each artefact and conglomerate artefacts, to check if necessary. Splitted by xslt stored in project-documentatation/Stylesheets/mdt_inscriptions/mdtArtefact_splitting.xsl
temporary= two files containing artefact or conglomerate artefacts used to render the html display. Made with xslt stored in project-documentatation/Stylesheets/mdt_inscriptions/mdtArtefact_start.xsl

build_to_xml.xml = launch the transformation for splitting the output file into several files sotred into temporary.
clone-projectDoc.xml = clone project-documentation for github action

.github/workflows
1- run csvtoxml.yml on push
2- run commacleaning.yml on finishing csvtoxml.yml task
3- run xmltoxmls.yml on finishing commacleaning.yml task 

csvtoxml.yml runs the xsl connected with API to run on all csv files. project-documentatation/Stylesheets/mdt_inscriptions/mdtArtefact_start.xsl => lines writing direclty with java into yml. 
commacleaning.yml runs on output files with project-documentation/stylesheets/mdt_inscriptions/mdt_CommaCleaning.xsl written directly into the yml with java. 
xmltoxmls.yml launcheds clone-projectDoc.xml then build_to_xml.xml. Files used form output folder to new splitted files are stroed into temporary folder. Launching project-documentation/stylesheets/mdt_inscriptions/mdtArtefact_splitting.xsl. 
