# scGSVA
## GSVA for single cell RNA seq analysis.   
# scGSVA [![Project Status:](http://www.repostatus.org/badges/latest/active.svg)](http://www.repostatus.org/#active)  [![](https://img.shields.io/badge/devel%20version-0.0.6-green.svg)](https://github.com/guokai8/scGSVA)  ![Code Size:](https://img.shields.io/github/languages/code-size/guokai8/scGSVA)
## Description
_scGSVA_ provides wrap functions to do GSVA analysis for single cell data. And scGSVA includes functions to build annotation for almost all species. scGSVA also provides function to generate figures based on the GSVA results.
_scGSVA_ provides functions to generate annotation data which can be used in the analysis.
## Installation
```
library(devtools)
install_github("guokai8/scGSVA")
``` 
## Examples
```{r}
set.seed(123)   
library(scGSVA)   
data(pbmc)
hsko<-buildAnnot(species="human",keytype="SYMBOL",anntype="KEGG")
res<-scgsva(pbmc,hsko)
vlnPlot(res,features="Wnt.signaling.pathway")
dotPlot(res,features="Wnt.signaling.pathway")
ridgePlot(res,features="Wnt.signaling.pathway")
featurePlot(res,features="Wnt.signaling.pathway")
Heatmap(res,group_by="celltype")
```   
## Note
The _scGSVA_ package use the __GSVA__ package to do the GSVA analysis for the single cell data.  The package is still under development.

## Contact information

For any questions please contact guokai8@gmail.com
