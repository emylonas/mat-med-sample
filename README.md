# Sample files from the Materia Medica project

## Overview

Our goal is to publish a website that contains an edition of an early modern herbal manuscript, Michiele's *Materia Medica* citation, together with accompanying material to show the gardens of Venice where the herbs might have been cultivated and the apothecary shops where they might have been dispensed. We began by focussing on the edition.

We wanted to be able to display the text, and to also be able to use it as a data source, and eventually, to make it available for re-use to other scholars. So we decided that the best format would be to mark it up using in XML according to the TEI schema. In order to do that, we had to find a machine readable text. Fortunately, there is a 1940s edition by xx DeToni, which Sabrina Minucci secured permission to use. We used the PDF of the DeToni edition, and OCRed it using the Google Cloud Vision API. The exising PDF contained OCRed text within it, but the accuracy of the Google API was significantly better. 

We then used regular expressions and simple scripts to add basic markup to the OCRed text files, in order to generate a valid TEI file. This process relied primarily on text featurs such as capitalized headings, blank lines and other regular textual features. We did not try to have an accurately marked up text, just a valid one. As the text would need proofreading regardless, and as we intended to enrich the existing text by specifying people. places and citations, corrections to the markup could be added during the editorial process.

Sabrina Minucci has been editing and enhancing the text using the OxygenXML software with a slightly modified TEI SimplePrint schema. Copies of the RDF and the ODD are in this repository.

In order to create a web site that is as simple and as future proof as possible, we decided to generate the edition and the accompanying pages using Jekyll, a static page generator that works both locally and is included in GitHub. We selected a Jekyll theme called Minimal Mistakes, which allows for a great deal of customization.          
