# Sample files from the Materia Medica project

## Overview

The goal of this project is to publish a website that contains an edition of an 16th c. herbal manuscript, Michiel's *I cinque libri di piante* (Marciana Library, Venice, Ms It. II, 26-30 (= 4860-64)), together with accompanying material to show the gardens of Venice where the herbs might have been cultivated and the apothecary shops where they might have been dispensed. We began by focussing on the edition.

We wanted to be able to display the text, and to also be able to use it as a data source, and eventually, to make it available for re-use to other scholars. We therefore decided to mark it up in XML according to the TEI schema. In order to do that, we had to find a machine readable text as a starting point. Fortunately, there is a [1940s edition by Ettore De Toni](https://gutenberg.beic.it/view/action/nmets.do?DOCCHOICE=2259962.xml&dvs=1633306544861~906&locale=en_US&search_terms=ettore+de+toni&show_metadata=true&adjacency=&VIEWER_URL=/view/action/nmets.do?&DELIVERY_RULE_ID=7&divType=&usePid1=true&usePid2=true), which Sabrina Minucci secured permission to use. We used the PDF of the DeToni edition, and OCRed it using the Google Cloud Vision API. The exising PDF contained OCRed text within it, but the accuracy of the Google API was significantly better. 

We then used regular expressions and simple scripts to add basic markup to the OCRed text files, in order to generate a valid TEI file. This process relied primarily on text featurs such as capitalized headings, blank lines and other regular textual features. We did not try to have an accurately marked up text, just a valid one. As the text would need proofreading regardless, and as we intended to enrich the existing text by specifying people. places and citations, corrections to the markup could be added during the editorial process.

Sabrina Minucci has been editing and enhancing the text using the OxygenXML software with a slightly modified TEI SimplePrint schema. Copies of the RDF schema and the ODD specification are in this repository.  The file "Marking up Michiel Documentation" (pdf file) is our working document that has details about encoding practices and decisions. It evolves as we encounter new features. 

In order to create a web site that is as simple and as future proof as possible, we decided to generate the edition and the accompanying pages using Jekyll, a static page generator that works both locally and is included in GitHub. We selected a Jekyll theme called Minimal Mistakes, which allows for a great deal of customization. You can see the work in progress here: [https://emylonas.github.io/xml-minimal/] and you can view the GitHub repository here: [https://github.com/emylonas/xml-minimal]. This summary does not yet document how the Jekyll theme works and what customizations we have added. Note that the site is incomplete and that many features don't work. 

## Rendering XML in the browser

An interesting feature of the Jekyll static page site is that we are not incorporating the edition text in the form of markdown directly into the site. We are, instead, using a javascript library called [CETEIcean](https://github.com/TEIC/CETEIcean) which can take an XML file and insert it into an HTML page, and then apply CSS or other formatting to it in the browser. This lets us take advantage of the richness of the TEI markup, but does not require any processing to happen on the server, in keeping with our minimal approach.

## Some useful links

* Jekyll https://jekyllrb.com/ and The Programming Historian ["Building a static site with Jekyll and GitHub Pages"](https://programminghistorian.org/en/lessons/building-static-sites-with-jekyll-github-pages)

