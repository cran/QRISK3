# QRISK3 R package

**Introduction**

This function allows you to calculate 10-year individual CVD risk using QRISK3-2017.


**Install from**


  **github**

    install.packages("devtools")

    library(devtools)

    install_github("YanLiUK/QRISK3")
  
   **CRAN**
     
    TBD
    install.packages("QRISK3")

**Example**

    data(QRISK3_2019_test)
    test_all <- QRISK3_2019_test

    test_all_rst <- QRISK3_2017(data=test_all, patid="ID", gender="gender", age="age",
    atrial_fibrillation="b_AF", atypical_antipsy="b_atypicalantipsy",
    regular_steroid_tablets="b_corticosteroids", erectile_disfunction="b_impotence2",
    migraine="b_migraine", rheumatoid_arthritis="b_ra", 
    chronic_kidney_disease="b_renal", severe_mental_illness="b_semi",
    systemic_lupus_erythematosis="b_sle",
    blood_pressure_treatment="b_treatedhyp", diabetes1="b_type1",
    diabetes2="b_type2", weight="weight", height="height",
    ethiniciy="ethrisk", heart_attack_relative="fh_cvd", 
    cholesterol_HDL_ratio="rati", systolic_blood_pressure="sbp",
    std_systolic_blood_pressure="sbps5", smoke="smoke_cat", townsend="town")

    test_all_rst$"QRISK_C_algorithm_score" <- test_all$"QRISK_C_algorithm_score"
    test_all_rst$"diff" <- test_all_rst$"QRISK3_2017_1digit" - test_all_rst$"QRISK_C_algorithm_score"
    print(test_all_rst$"diff")
    print(identical(test_all_rst$"QRISK3_2017_1digit", test_all_rst$"QRISK_C_algorithm_score"))

**Paper about how to create QRISK3 variables**

    TBD
