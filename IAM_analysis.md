IAM dataset
=====================

_Published_ -> The database was first published in at the ICDAR 1999.  
About dataset
------------------
The database contains forms of unconstrained handwritten text, which were scanned at a resolution of 300dpi and saved as PNG images with 256 gray levels. 

The IAM Handwriting Database 3.0 is structured as follows:
- 657 writers contributed samples of their handwriting
- 1'539 pages of scanned text
- 5'685 isolated and labeled sentences
- 13'353 isolated and labeled text lines
- 115'320 isolated and labeled words

The words have been extracted from pages of scanned text using an automatic segmentation scheme and were verified manually. 
- Paper name (P030) - Automatic Segmentation of the IAM Off-line Database for Handwritten English Text
- Authors Matthias Zimmermann, Horst Bunke
- Link - http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.652.1885&rep=rep1&type=pdf


Reading dataset
----------------
- form.txt
  - format: a01-000u 000 2 prt 7 5 52 36
  - a01-000u  -> form id
  - 000       -> writer id
  - 2         -> number of sentences
  - prt       -> word segmentation
    - prt: some lines correctly segmented
    - all: all lines correctly segmented
  - 7 5       -> 5 of 7 lines are correctly segmented into words
  - 52 36     -> the form contains 52 words, 36 are in lines which have been correctly segmented
- words.txt
  - format: a01-000u-00-00 ok 154 1 408 768 27 51 AT A
  - a01-000u-00-00  -> word id for line 00 in form a01-000u
  - ok              -> result of word segmentation
    - ok: word was correctly
    - er: segmentation of word can be bad
  - 154             -> graylevel to binarize the line containing this word
  - 1 -> number of components for this word
  - 408 768 27 51   -> bounding box around this word in x,y,w,h format
  - AT -> the grammatical tag for this word, see the file tagset.txt for an explanation
  - A -> the transcription for this word




About XML labeling
------------------

- All form, line and word images are provided as PNG files.
- The corresponding form label files, including segmentation information and variety of estimated parameters (from the preprocessing steps described in P031) are included in the image files as meta-information in XML format which is described in XML file and XML file format (DTD).


Error Files
------------
a01-117-05-02.png
r06-022-03-05.png