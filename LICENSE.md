Copyright [2025] [Xiang Wang]

# LICENSE TERMS
The following materials (collectively "Materials") are governed by this license:

* Behavioural Data: 

  SPSS files (.sav/.csv) encoded per *Section 4.1*.

  Excel files (.xlsx) and DAT files (.dat) were tranformed from SPSS files. 

* Neuroimaging Data: 

  NIfTI-1.1 format files (.nii) with anonymized headers.

  MATLAB binary files (.mat) containing preprocessed FC matrices.

* Code:

  R scripts (version ≥4.2.0) dependent on bootnet, qgraph, and networkcomparison.

  Mplus script based on Mplus 8.3.0


## 1. Permitted Use
### 1.1 Replication Scope

You may copy, distribute, display, and perform the Materials solely to replicate results from the article:
"Unveiling Diverse Clinical Symptom Patterns and Neural Activity Profiles in Major Depressive Disorder Subtypes" ("Designated Paper").

Note: A DOI will be added to this clause upon publication.

### 1.2 Additional Use

Any use beyond replication (including commercial purposes, public dissemination, or new research) requires a signed authorization form (template in Appendix A).

## 2. Prohibited Use
### 2.1 Research Restrictions

No New Publications: The Materials may not be used to publish new findings (including preprints, conference abstracts, or derivative datasets).

Verification Exception: Using the Materials to validate existing published studies is permitted if no derivative works are generated.

### 2.2 Modification Restrictions

Technical Modifications: Code may be adapted for compatibility (e.g., updating file paths) if scientific integrity is preserved.

Substantive Modifications: Any changes to algorithms, data processing pipelines, or neural activity metrics require written permission.

### 2.3 Privacy Violations

De-anonymization Ban: Attempting to re-identify individuals from neuroimaging data (e.g., reconstructing facial features, correlating with external databases) is strictly prohibited.

Technical Safeguards: NIfTI headers have been sanitized using DPARSF V5.2.

### 2.4 Open-Source Compliance

The R packages (bootnet, qgraph, networkcomparison) are licensed under GPL-2/3. Users must comply with both this license and the original package licenses.

### 2.5 FC Matrix Restrictions

Reverse Engineering: Attempting to derive raw fMRI time series or participant-level identifiers from FC matrices is prohibited.

Matrix Manipulation: Rescaling or normalizing FC matrices for purposes beyond replication requires written permission.

## 3. Attribution
### 3.1 Mandatory Citations

Any public use must include:

(a) Attribution to "[Xiang Wang]" as the original author;

(b) Citation to the Designated Paper (DOI pending).

### 3.2 Open-Source Credit

Publications using the code must cite:

* ***qgraph***: Epskamp, S., Cramer, A. O., Waldorp, L. J., Schmittmann, V. D., & Borsboom, D. (2012). qgraph: Network visualizations of relationships in psychometric data. Journal of statistical software, 48, 1-18.

* ***bootnet***: Epskamp, S., & Fried, E. I. (2015). Package ‘bootnet’. Bootstrap methods for various network estimation routines, 5(0.1).

* ***networkcomparisontest***: van Borkulo, C., Boschloo, L., Borsboom, D., Penninx, B. W. J. H., Waldorp, L., & Schoevers, R. (2015). Package ‘NetworkComparisonTest’. JAMa Psychiatry, 72, 1219-1226.

### 3.3 License Propagation

All distributed copies must retain this license and original package licenses.

## 4. Data Standards
### 4.1 Behavioural Data Encoding

SPSS Standards:

* Variable names: lowercase_with_underscores (e.g., P_FrameCensored).

* Missing values: Coded as -999 with documentation in metadata.sps.

* Categorical variables: Numeric codes with labels (e.g., 1="Male").

### 4.2 Neuroimaing Data

#### 4.2.1 ALFF, fALFF, ReHo maps (NIfTI Data)

NIfTI Specifications:

* Orientation: MNI152 space (ICBM 2009a nonlinear symmetric).

* Resolution: 2mm isotropic voxels.

* File naming: [Modality]_[Group][ID].nii (e.g., ALFFMap_MDD001.nii).
  
* Preprocessing pipeline (Dpabi toolbox standard pipeline)

#### 4.2.2 Functional Connectivity Matrices

File Format: MATLAB .mat files containing 2D matrices.

Matrix Specifications:

* Dimensions: [N_ROI x N_ROI] (N_ROI = 122, based on [Schaefer multiresolution atlas](https://github.com/ThomasYeoLab/CBIG/tree/master/stable_projects/brain_parcellation/Schaefer2018_LocalGlobal) and [Xiao’s structural connectomic atlas](https://osf.io/p7syt/).

* Normalization: Fisher-Z transformed correlation coefficients.

* Symmetry: Enforced to be symmetric with diagonal = 'Inf'.

* Metadata: Each .mat file includes a 'name' field, which is a string that represents the subject's unique identifier.

* Atlas used (Schaefer multiresolution atlas and  Xiao’s structural connectomic atlas).

* Preprocessing pipeline: [DPARSF V5.2](https://rfmri.org/DPABI)

### 4.3 Code Implementation

#### R scripts require version ≥4.2.0, and the users must manually install the following packages:
  * bootnet
  * qgraph
  * networkcomparison
#### Mplus scripts requires version ≥ 8.3.0

## 5. Disclaimer
### 5.1 No Warranty

The Materials are provided "AS IS" without warranties of accuracy, completeness, or fitness for any purpose.

### 5.2 Liability Exclusion

The author is not liable for direct, indirect, or consequential damages arising from use of the Materials.

## 6. Termination
### 6.1 Automatic Termination

Violation of any term immediately revokes all rights.

Upon termination, users must:

(a) Cease all use;

(b) Destroy all copies (including backups).

## 7. Governing Law
This license is governed by Chinese law.

Disputes shall be resolved exclusively in Beijing courts.

## 8. Duration
This license remains effective until explicitly revoked in writing by [Xiang Wang].

Appendix A: Authorization Form Template
Available upon request from the [first author](xiangwangpsy@163.com) or the [corresponding author](xiongzhaozhu@csu.edu.cn).

## ***Final Notes***

* Ethics Compliance: Users must adhere to their institutional ethics guidelines when handling these Materials.

* Breach Reporting: Suspected privacy breaches (e.g., accidental re-identification) must be reported within 24 hours.
