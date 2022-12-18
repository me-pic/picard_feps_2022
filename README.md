> :warning: This section is under construction :construction_worker_woman:

# Code for Picard et al., Title

## Notes

The scripts were developed to analyze already preprocessed trial-by-trial fMRI contrast images (hdr/img files). The data used in 
this study come from Kunz et al. (2012) study. The data were not in BIDS format, thus the scripts might not directly work on BIDS 
organized data. Each script can be run separately (see the documentation below), but a main script 
([main.py](https://github.com/me-pic/picard_feps_2022/blob/main/scripts/main.py)) is provided to run the complete analysis pipeline.

The preprocessing of the data and the first level analysis were performed using SPM8. Details about those steps can be found in the Method section of the article.

The brain signatures used for the similarity analyis can be found below:
- NPS: on request from Tor Wager
- [SIIPS](https://github.com/canlab/Neuroimaging_Pattern_Masks/tree/master/Multivariate_signature_patterns/2017_Woo_SIIPS1) 
- [PVP](https://github.com/canlab/Neuroimaging_Pattern_Masks/tree/master/Multivariate_signature_patterns/2022_coll_pain_monetary_reward_decision_value)
- [MAThS](https://github.com/canlab/Neuroimaging_Pattern_Masks/tree/master/Multivariate_signature_patterns/2021_Ceko_MPA2_multiaversive) 

## LASSO-PCR analysis

## Permutation tests

## Bootstrap analysis

## Similarity analysis
The similarity analysis can be run independently of the other scripts with [similarity.py](https://github.com/me-pic/picard_feps_2022/blob/main/scripts/similarity.py)

<b>How to launch the similarity script:</b>
<br>`python ./similarity.py --path_signature '/path/to/signature' --path_feps '/path/to/feps/or/any/other/signature' --path_output 
'/path/to/output'`
- --path_signature: specifies the path to the signature Nifti file on which to compute the spatial similarity
- --path_feps: specifies the path to the feps Nifti file (or any other signature) on which to compute the spatial similarity
- --path_output: specifies the path to output the results

## Visualization
The visualization script can be run with [visualization.py](https://github.com/me-pic/picard_feps_2022/blob/main/scripts/visualization.py). The fonts and the disposition of the figures were edited using Adobe 
Illustrator.

<b>How to launch the visualization script:</b>
<br>`python ./visualization.py --path_output '/path/to/output' --path_feps '/path/to/feps' 
--path_behavioral '/path/to/behavioral/measures' --path_dot_product '/path/to/dot/product' 
--path_performance '/path/to/performance/metrics' --path_y_test 'path/to/y/test' --path_y_pred 
'/path/to/y/pred' --path_siips_similarity_networks '' --path_pvp_similarity_networks '' --path_maths_similarity_networks ''`
- --path_output: specifies the path to output the figures
- --path_feps (optional): specifies the path to the feps Nifti file. If not specified, the 
signature weights will not be plotted 
- --path_behavioral (optional): specified the path to the csv file containing the behavioral 
measures
- --path_dot_product (optional): specified the path to the npy file containing the dot product 
values between a signature weights and the FACS scores. If not specified, the correlation between 
the signature expression and the FACS scores will not be plotted
 - --path_performance (optional): specifies the path to the csv file containing the 
performance 
metrics of the model. If not specified, the violin plot of the model performance will not be 
plotted
- --path_y_test (optional): specifies the path to the pickle file containing the y_test values. If 
not specified, the regression plot of the model performance will not be plotted
- --path_y_pred (optional): specifies the path to the pickle file containing the y_pred values
- --path_siips_similarity_networks (optional): specifies the path to pickle file containing the spatial similarity metrics between the FEPS and the SIIPS-1. If not specified, the spatial similarity barplots across networks are not plotted
- --path_pvp_similarity_networks (optional): specifies the path to pickle file containing the spatial similarity metrics between the FEPS and the PVP
- --path_maths_similarity_networks (optional): specifies the path to pickle file containing the spatial similarity metrics between the FEPS and the MAThS
