Mission project based on the participation on the neuroimaging open source software 
PyHRF
Applicant: Martin Perez­Guevara 
Academic supervisors: Philippe Ciuciu and Christophe Pallier 
Software engineering supervisor: Thomas Perret 
 
# Contributions to the PyHRF open source software “Development of state­of­the­art neuroimaging simulations” 
 
## Aims of the project 
 
The   main   goal   of   the   project   is   to   develop   a   realistic   functional   magnetic   resonance   imaging (fMRI)   data   simulator.   It   will   help   researchers   explore   the   power   of   experimental   design,   assess the   limit   of   analysis   methods   (for   example   assuming   the   canonical   HRF   model)   and   explore   the influence   of   different   sources   of   noise   on   fMRI   results.   To   achieve   this   I   will   take   advantage   of   the tools   already   developed   in   PyHRF.   This   package,   formerly   developed   by   Philippe   Ciuciu   and Thomas   Vincent   in   the   PARIETAL/INRIA   team   extensively   explored   the   problem   of   joint   activation detection   and   HRF   estimation   as   an   alternative   to   the   standard   assumptions   in   fMRI   data analysis.   It   already   embeds   a   2D   simulator   platform   of   hemodynamic   activity.   Moreover,   starting this   year,   a   research   engineer   was   hired   by   the   research   team   to   refactor   the   software   code   and a   bigger   community   is   getting   involved   to   boost   the   structure,   capabilities   and accessibility   of   the packages under an open source philosophy. 
 
## Work plan (32 days plan) 
 
The development steps of the project would be: 
 
1. Build the 3D spatial support of the system (5 days) 
1.1. Select and document real datasets to use as template and to extract parameters afterwards. 
1.2. Create the interface to inject the 3D datasets into the framework
2. Develop tools to generate binary clusters in 3D (activation maps) constrained by the cortical mask. Should include parameters related to scale and shape (5 days) 
3. Work on the Implementation of methods to inform, from the real datasets, the parameters of the simulation steps algorithms: (11 days) 
3.1. The developed binary activation maps (3 days) 
3.2. The artificially generated hemodynamic response, considering the JDE proposed HRF models (3 days) c. The physiological (hemodynamic) noise, considering physiological models implemented already in PyHRF (3 days) 
3.3. The acquisition related noise, like movement, considering the information available from well established preprocessing techniques (2 days)  
4. Validate the generation of the 3D artificial datasets (5 days)  
5. Work on the development of tools to assist the comparison of experimental designs in the case of the GLM and JDE pipelines (6 days). 
5.1. Related to design efficiency 
5.2. Related to adjusting parameters according to stimuli specific hypothesis for which previous experimental data is available. 
 
## Impact of the project 
 
This project will provide an interesting open source tool to the broad neuroimaging research community and particularly strengthen the collaboration between the language neuroimaging team UNICOG and the signal processing, image analysis and machine learning team PARIETAL at NeuroSpin. 
 
Moreover it is expected that this project will: 
 
- Extend the study of the methods already implemented in the platform to the more realistic 3D case. 
- Open the possibility to test different sources of noise and physiological models, also informed by real datasets. 
- Open the possibility to study experimental design hypothesis to compare and aggregate them in a systematic way but still adaptable to specific experimental cases. 
- Open the possibility to compare fMRI data analysis pipelines in a systematic way. 
 
## Context of the project 
 
Currently,   the   analyses   of   fMRI   data   mostly   rely   on   linear   regressions   based   on   a   “canonical” HRF   (Hemodynamic   Response   Function).   This   model   of   the   HRF   originates   from measurements   made   in   visual   areas   and   it   is   known   that   it   can   fit   less   well   the responses   in  other   brain   areas.   Various   algorithms   have   been   developed   to   tackle   the   problem   of   estimating  the   HRF   in   order   to   improve   the   interpretation   of   activations   in   brain   areas   that   are   different   from  visual areas and, also to characterize it  across subjects.  Pyhrf   is   a   set   of   tools   for   within­subject   fMRI   data   analysis,   focused   on   the   characterisation   of   the  hemodynamics 1 . This   set   of   open   source   tools   helps   close   the   gap   between   the   latest   signal processing   techniques   and   FMRI   research 2 .   The   software   is   mainly   written   in   Python,   with   some ­C-extension   that   handle   computation   intensive   parts   of   the   algorithms.   Also   the   package   relies on classical   scientific   libraries:   numpy,   scipy,   matplotlib as   well   as   Nibabel   to   handle input/outputs and NiPy which provides tools for functional data analysis 1 .  
 
Adding   simulation   tools   to   this   software   is   an   important   step   to   assist   the   study   of   the   rest   of   the  fMRI   processing   pipelines   and   to   assist   experimental   design   by   considering   measures of  efficiency,   although   this   still   have   not   been   completely   explored   with   the   package.   Currently   it   is possible   to   simulate   different   types   of   stimulus   induced   signals   and   noise   in   two   dimensional maps.   However   to   be   able   to   exploit   all   the   potential   of   the   mentioned   tools   some development   is still   necessary.   In   particular   the   extension   of   the   models   to   more   realistic   three­dimensional simulations with similar properties to those of real data.