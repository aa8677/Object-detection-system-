
install.packages("devtools")
 devtools::install_github("bnosac/image", subdir = "image.darknet", build_vignettes = TRUE)

library(image.darknet) 
setwd="C:\Users\DELL\Downloads\ARABIAN HORSE.jpeg"
darknet_model<-image_darknet_model(type = "classify",
                                   model="tiny.cfg",
                                    weights=system.file(package = "image.darknet","models","tiny.weights"),
                                   labels = system.file(package = "image.darknet","include","darknet","data","imagenet.shortnames.list"))
image_darknet_classify(file = "C:\Users\DELL\Downloads\ARABIAN HORSE.jpeg",
                       object = darknet_model)
darknet_model<-image_darknet_model(type = "detect",
                                   model="tiny-yolo-voc.cfg",
                                   weights=system.file(package = "image.darknet","models","tiny-yolo-voc.weights"),
                                   labels = system.file(package = "image.darknet","include","darknet","data","voc.names"))
image_darknet_detect(file = "C:\Users\DELL\Downloads\ARABIAN HORSE.jpeg",
                       object = darknet_model)
