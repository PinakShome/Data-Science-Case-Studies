# Microsoft-Malware-detection

## What is Malware?
The term malware is a contraction of malicious software. Put simply, malware is any piece of software that was written with the intent of doing harm to data, devices or to people. 
Source: https://www.avg.com/en/signal/what-is-malware

## Problem Statement
In the past few years, the malware industry has grown very rapidly that, the syndicates invest heavily in technologies to evade traditional protection, forcing the anti-malware groups/communities to build more robust softwares to detect and terminate these attacks. The major part of protecting a computer system from a malware attack is to identify whether a given piece of file/software is a malware.

## Source/Useful Links
Microsoft has been very active in building anti-malware products over the years and it runs it’s anti-malware utilities over 150 million computers around the world. This generates tens of millions of daily data points to be analyzed as potential malware. In order to be effective in analyzing and classifying such large amounts of data, we need to be able to group them into groups and identify their respective families. 

This dataset provided by Microsoft contains about 9 classes of malware. ,

**Source:** https://www.kaggle.com/c/malware-classification

## Real-world/Business objectives and constraints.
1. Minimize multi-class error.
2. Multi-class probability estimates.
3. Malware detection should not take hours and block the user's computer. It should finish in a few seconds or a minute

## Performance Metric

Metric(s):

* Multi class log-loss
* Confusion matrix

## Observations
* asm image feature found to be the best
* XGBOOST took the most of the time to run as compared to other models
* Out of  65k features, **2000** features of bigram byte file preserved almost **99% of variance**.
* Best log loss was obtained in case of XGBOOST in every case
* Best log loss for cv obtained is 0.004

## Summary
#### Bytes Feature Summary
![Bytes Alone](/bytes.png)

#### ASM Feature Summary
![ASM Alone](/asm.png)

#### Combine Feature Summary
!![Combined](/combine.png)


## Referances

* http://blog.kaggle.com/2015/05/26/microsoft-malware-winners-interview-1st-place-no-to-overfitting/ 
* https://arxiv.org/pdf/1511.04317.pdf 
* First place solution in Kaggle competition: https://www.youtube.com/watch?v=VLQTRlLGz5Y 
* https://github.com/dchad/malware-detection 
* http://vizsec.org/files/2011/Nataraj.pdf 
* https://www.dropbox.com/sh/gfqzv0ckgs4l1bf/AAB6EelnEjvvuQg2nu_pIB6ua?dl=0 
