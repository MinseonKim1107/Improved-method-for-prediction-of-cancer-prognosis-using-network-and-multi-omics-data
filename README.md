# Improved-method-for-prediction-of-cancer-prognosis-by-network-learning


## Welcome to our Git Repository!

## 1.setting

  Python  3.6.3
  
  numpy 1.14.2
  
  sklearn 0.19.1
  
  scipy 1.0.0
  
  tensorflow 1.6.0
  

## 2.  Data
   #### 1> Download URL
: https://www.dropbox.com/sh/tp70gitmmtaft0l/AABLSniRI9lCo1ZqtUGL4ZOqa?dl=0
  
   #### 2>
   ##### (1) mRNA
        :Comma-delimited file of gene expression data 
           Ex)  ,patient1, patient2, patient3
               gene1,-4.556,-1.784,2.295
               gene2,-1.923,1.603,-2.696         
   ##### (2) CNA
         :Comma-delimited file of copy number data 
          Ex)  , patient1, patient2, patient3
              gene1,-0.536,-0.464,8.025
              gene2,7.022,-1.033,-0.636        
   ##### (3) METHYLATION
          :Comma-delimited file of DNA methylation data
           Ex)  , patient1, patient2, patient3
               gene1,7.356,6.404,2.305
               gene2,1.002,3.082,0.006           
   ##### (4) SNP
          :Comma-delimited file of somatic mutation data
           Ex)  , patient 1, patient 2, patient 3
               gene1,0,1,0
               gene2,0,0,4
              
   ##### (5) CLINICAL_FILE
          :Comma-delimited file of Patient's names and osevent
           Ex) patient1,0
               patient2,1
               patient3,0     
  ##### (6) NETWORK
          : Comma-delimited file of PPI network
           EX) GENE,GENE
              gene1, gene2
              gene1, gene3
              gene4, gene5
         
## 3. Run
   ##### python ImprovedMethod.py [-t topNgeneInTTest][-i iteration][-n ngene][-d dampingfactor][-l limit_of_iteration] mRNA CNA METHYLATION SNP CLINICAL_FILE NETWORK
  

    
    - topNgeneInTTest : Top N gene showed statistical differences between the means of good and poor sample groups. ( Default: 400 )
    - iteration: to select a stable and robust feature for random initialization of weights, N iteration in GANs and PageRank. ( Default : 5 )
    - ngene : N genes selected as biomarker. ( Default: 250 )
    - dampingfactor : damping factor in PageRank. ( Default: 0.7 )
    - limit_of_iteration : Parameter of step2,3. When step2 and step3 are repeated N times, the genes that appeared K times in N times is selected as biomarkers. The K is the limit of iteration. ( Default : 5)

###   Ex) python ImprovedMethod.py BRCA_mRNA.txt BRCA_CNA.txt BRCA_methylation.txt BRCA_SNP.txt BRCA_clinical.txt FIsnetwork.txt

    1.preprocessing data...
     loading data...
     divide samples for 10fold validation
     0fold ttest start





