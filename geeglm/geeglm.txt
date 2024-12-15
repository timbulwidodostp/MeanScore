# Olah Data Semarang
# WhatsApp : +6285227746673
# IG : @olahdatasemarang_
# Fit a geeglm model using MeanScore (MIIPW) With (In) R Software
install.packages("MIIPW")
library("MIIPW")
geeglm = read.csv("https://raw.githubusercontent.com/timbulwidodostp/MeanScore/main/geeglm/geeglm.csv",sep = ";")
# Estimation Fit a geeglm model using MeanScore (MIIPW) With (In) R Software
formula<-C6kine~ActivinRIB+ActivinRIIA+ActivinRIIAB+Adiponectin+AgRP+ALCAM
pMat<-mice::make.predictorMatrix(geeglm[names(geeglm)%in%all.vars(formula)])
geeglm<-MeanScore(data=geeglm,formula<-formula,id='ID',visit='Visit',family='gaussian',init.beta = NULL,
init.alpha=NULL,init.phi=1,tol=.00001,weights = NULL, corstr = 'exchangeable',maxit=50,m=2,pMat=pMat)
summary_meanscore(geeglm)
# Fit a geeglm model using MeanScore (MIIPW) With (In) R Software
# Olah Data Semarang
# WhatsApp : +6285227746673
# IG : @olahdatasemarang_
# Finished