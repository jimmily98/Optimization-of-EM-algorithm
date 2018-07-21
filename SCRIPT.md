# Optimization-of-EM-algorithm
# Issued by Jimmily98


library(DEsingle)

#get data from middle_result

DEsingle.res<-read.csv("C:/Users/LHG/Desktop/middle_result.csv")

DEsingle.res.DEg <- DEsingle.res[which(DEsingle.res$Type == "DEg"),]

DEsingle.res.DEa <- DEsingle.res[which(DEsingle.res$Type == "DEa"),]

DEsingle.res.DEs <- DEsingle.res[which(DEsingle.res$Type == "DEs"),]

DEsingle.res.nDE <- DEsingle.res[which(is.na(DEsingle.res$Type)),]


#generate the average of parametres_g
theta1_g<-sum(DEsingle.res.DEg[,2])/length(DEsingle.res.DEg[,2])

theta2_g<-sum(DEsingle.res.DEg[,3])/length(DEsingle.res.DEg[,3])

mu1_g<-sum(DEsingle.res.DEg[,4])/length(DEsingle.res.DEg[,4])

mu2_g<-sum(DEsingle.res.DEg[,5])/length(DEsingle.res.DEg[,5])

size1_g<-sum(DEsingle.res.DEg[,6])/length(DEsingle.res.DEg[,6])

size2_g<-sum(DEsingle.res.DEg[,7])/length(DEsingle.res.DEg[,7])

prob1_g<-sum(DEsingle.res.DEg[,8])/length(DEsingle.res.DEg[,8])

prob2_g<-sum(DEsingle.res.DEg[,9])/length(DEsingle.res.DEg[,9])


#generate the average of parametres_a
theta1_a<-sum(DEsingle.res.DEa[,2])/length(DEsingle.res.DEa[,2])

theta2_a<-sum(DEsingle.res.DEa[,3])/length(DEsingle.res.DEa[,3])

mu1_a<-sum(DEsingle.res.DEa[,4])/length(DEsingle.res.DEa[,4])

mu2_a<-sum(DEsingle.res.DEa[,5])/length(DEsingle.res.DEa[,5])

size1_a<-sum(DEsingle.res.DEa[,6])/length(DEsingle.res.DEa[,6])

size2_a<-sum(DEsingle.res.DEa[,7])/length(DEsingle.res.DEa[,7])

prob1_a<-sum(DEsingle.res.DEa[,8])/length(DEsingle.res.DEa[,8])

prob2_a<-sum(DEsingle.res.DEa[,9])/length(DEsingle.res.DEa[,9])


#generate the average of parametres_s
theta1_s<-sum(DEsingle.res.DEs[,2])/length(DEsingle.res.DEs[,2])

theta2_s<-sum(DEsingle.res.DEs[,3])/length(DEsingle.res.DEs[,3])

mu1_s<-sum(DEsingle.res.DEs[,4])/length(DEsingle.res.DEs[,4])

mu2_s<-sum(DEsingle.res.DEs[,5])/length(DEsingle.res.DEs[,5])

size1_s<-sum(DEsingle.res.DEs[,6])/length(DEsingle.res.DEs[,6])

size2_s<-sum(DEsingle.res.DEs[,7])/length(DEsingle.res.DEs[,7])

prob1_s<-sum(DEsingle.res.DEs[,8])/length(DEsingle.res.DEs[,8])

prob2_s<-sum(DEsingle.res.DEs[,9])/length(DEsingle.res.DEs[,9])


#generate the average of parametres_n
theta1_n<-sum(DEsingle.res.DEn[,2])/length(DEsingle.res.DEn[,2])

theta2_n<-sum(DEsingle.res.DEn[,3])/length(DEsingle.res.DEn[,3])

mu1_n<-sum(DEsingle.res.DEn[,4])/length(DEsingle.res.DEn[,4])

mu2_n<-sum(DEsingle.res.DEn[,5])/length(DEsingle.res.DEn[,5])

size1_n<-sum(DEsingle.res.DEn[,6])/length(DEsingle.res.DEn[,6])

size2_n<-sum(DEsingle.res.DEn[,7])/length(DEsingle.res.DEn[,7])

prob1_n<-sum(DEsingle.res.DEn[,8])/length(DEsingle.res.DEn[,8])

prob2_n<-sum(DEsingle.res.DEn[,9])/length(DEsingle.res.DEn[,9])


#export the matrix
DEg_aver<-c(theta1_g,theta2_g,mu1_g,mu2_g,size1_g,size2_g,prob1_g,prob2_g)

DEa_aver<-c(theta1_a,theta2_a,mu1_a,mu2_a,size1_a,size2_a,prob1_a,prob2_a)

DEs_aver<-c(theta1_s,theta2_s,mu1_s,mu2_s,size1_s,size2_s,prob1_s,prob2_s)

DEn_aver<-c(theta1_n,theta2_n,mu1_n,mu2_n,size1_n,size2_n,prob1_n,prob2_n)

average_matrix<-DEg_aver

average_matrix<-rbind(average_matrix,DEa_aver)

average_matrix<-rbind(average_matrix,DEs_aver)

average_matrix<-rbind(average_matrix,DEn_aver)

colnames(average_matrix)<-c("theta_1","theta_2","mu_1","mu_2","size_1","size_2","prob_1","prob_2")
rownames(average_matrix)<-c("DEg","DEa","DEs","nDE")
write.csv(average_matrix,file="average_matrix.csv")


































