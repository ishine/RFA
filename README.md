# RFA
2021-08-16  
This repository is for the code which implements the Rhythm Formant Analysis methodology for Rhythm Formant Theory, as described in  the following publication:  
Gibbon, Dafydd. 2021. The rhythms of rhythm. *Journal of the International Phonetic Association*, 16 August 2021, 1-33. First View. (online, open access)
https://www.doi.org/10.1017/S0025100321000086  
  
**2022-04-19 The original intention was to publish the code when the article appears in print. Since there is a print backlog, here it is anyway. Basic overview information is below.**  

##MIT license  
Begin license text.  
Copyright 2021 Dafydd Gibbon  
Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:  
The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.  
THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.  
End license text.  
  
----------------------------------------------------------  
  
##Workflow examples  
  
1. Visualisation of low frequency spectra and spectrograms:  
In directory RFA_single_signal_processing, run  
rfa_single.py DATA/Female_English_German/RT_E1.wav  
The graph is displayed after several seconds, and a copy is kept in directory FIGURES.  
  
2. Comparison of low frequency property vectors of different files:  
2.1. In directory RFA_multiple_signal_processing, run  
rfa_mult.py DATA/Female_English_German/RT_E1.wav  
The CSV file outputs are in the CSV directory.  
2.2. In directory RFA_multiple_signal_processing, run  
numdistnetdendro.py CSV/lfammaxfreqs.csv  
The hierarchical clustering (dendrogram) output is in directory DENDRO.  
The distance network outputs are in directory GRAPHVIZ.  
  
----------------------------------------------------------    
  
##NOTE:  
This software requires the following items to be installed:  
- Python3  
- NumPy (pip numpy)  
- SciPy (pip scipy)  
- GraphViz (pip graphviz)  
- GraphViz (GraphViz for Windows or Linux)  
When installing GraphViz for Windows or Linux,  
make sure that it can access the system path.  
  
----------------------------------------------------------  
  
##DIRECTORY AND FILE LISTING  
  
README.1st                      this file  
RFA_multiple_signal_processing  signal processing and comparison  
RFA_single_signal_processing    signal processing and visualisation  
  
./RFA_multiple_signal_processing:  
CSV                             CSV output of rfa_mult.py, input to rfa_mult.py
DATA                            DATA directories for input to rfa_mult.py  
DENDRO                          Dendrogram figure outputs from numdistnetdendro.py  
GRAPHVIZ                        Distance net figure outputs from numdistnetdendro.py  
module_F0.py                    F0 extraction module (AMDF) for rfa_mult.py  
module_spectrogram.py           Spectrogram creation module for rfa_mult.py  
numdistnetdendro_conf.py        Configuration file for numdistnetdendro.py  
numdistnetdendro.py             Main module, clusters from CSV: hierarchical, nets  
rfa_mult_conf.py                Configuration file for rfa_mult.py  
rfa_mult.py                     Main module, generates CSV files from DATA  
  
./RFA_multiple_signal_processing/DATA:  
Female_English_German          Sample data for clustering  
  
./RFA_single_signal_processing:  
DATA                           DATA directories for input to rfa_single.py  
FIGURES                        PNG graphics output from rfa_single.py  
module_dendrogram.py           Dendrogram creation module for rfa_single.py  
module_F0.py                   F0 extraction module (AMDF) for rfa_single.py  
module_spectrogram.py          Spectrogram creation module for rfa_single.py  
rfa_single_conf.py             Configuration file for rfa_single.py  
rfa_single.py                  Main module, generates graphics from DATA  
  
./RFA_single_signal_processing/DATA:  
English_male_MLK01.wav               MLK  
English_male_one-to-seven.wav        English counting  
English_male_one-to-thirty_16k.wav   English counting  
Female_English_German                Directory with sample data  
Putonghua_female_one-to-seven.wav    Mandarin Chinese counting  
sine-200x5x6.wav                     Calibration data  
