
library(R.utils)
paste(intToBin(41190))
[1] "1010000011100110"
(paste(rev(as.integer(intToBits(41190))),collapse = ""))
[1] "00000000000000001010000011100110"
substr(paste(rev(as.integer(intToBits(41190))),collapse = ""),17,32)
[1] "1010000011100110"

for (i in seq_along(MODIS$StateQA)){
  MODIS$QA2bin[i] <- substr(paste(rev(as.integer(intToBits(MODIS$StateQA[i]))),collapse = ""),22,22)
}
library(R.utils)
paste(intToBin(41190))
[1] "1010000011100110"
(paste(rev(as.integer(intToBits(41190))),collapse = ""))
[1] "00000000000000001010000011100110"
substr(paste(rev(as.integer(intToBits(41190))),collapse = ""),17,32)
[1] "1010000011100110"

# paste(intToBin(1025))
# (paste(rev(as.integer(intToBits(1024))),collapse = ""))
# substr(paste(rev(as.integer(intToBits(1024))),collapse = ""),22,22)
for (i in seq_along(MODIS$StateQA)){
  MODIS$QA2bin[i] <- substr(paste(rev(as.integer(intToBits(MODIS$StateQA[i]))),collapse = ""),22,22)
}

鸡翅包子番茄是好兄弟 23:30:04
library(R.utils)
paste(intToBin(41190))
[1] "1010000011100110"
(paste(rev(as.integer(intToBits(41190))),collapse = ""))
[1] "00000000000000001010000011100110"
substr(paste(rev(as.integer(intToBits(41190))),collapse = ""),17,32)
[1] "1010000011100110"
for (i in seq_along(MODIS$StateQA)){
  MODIS$QA2bin[i] <- substr(paste(rev(as.integer(intToBits(MODIS$StateQA[i]))),collapse = ""),22,22)
}
samplestemp<-samplestemp%>%
  st_transform(21097)
samplestemp
Kenoutline<-Kenoutline%>%
  st_transform(21097)

samplestempsp<-samplestemp%>%
  as(.,'Spatial')
Kenoutlinesp<-Kenoutline%>%
  as(.,'Spatial')
emptygrd<-as.data.frame(spsample(Kenoutlinesp,n=1000,type = "regular",cellsize=60000))
names(emptygrd)<-c("X", "Y")
plot(emptygrd)
coordinates(emptygrd)<-c("X", "Y")
gridded(emptygrd)<-TRUE #create SpatialPixel object
fullgrid(emptygrd)<-TRUE #create SpatialGrid object
proj4string(emptygrd)<-proj4string(samplestempsp)

p_load(gstat)

interpolate<-gstat::idw(Jan~1, samplestempsp, newdata=emptygrd, idp=2.0)
ras<-raster(interpolate)%>%
  mask(.,Kenoutline)
plot(ras)
samplestemp<-samplestemp%>%
  st_transform(21097)
samplestemp
Kenoutline<-Kenoutline%>%
  st_transform(21097)

samplestempsp<-samplestemp%>%
  as(.,'Spatial')
Kenoutlinesp<-Kenoutline%>%
  as(.,'Spatial')
emptygrd<-as.data.frame(spsample(Kenoutlinesp,n=1000,type = "regular",cellsize=60000))
names(emptygrd)<-c("X", "Y")
plot(emptygrd)
coordinates(emptygrd)<-c("X", "Y")
gridded(emptygrd)<-TRUE #create SpatialPixel object
fullgrid(emptygrd)<-TRUE #create SpatialGrid object
proj4string(emptygrd)<-proj4string(samplestempsp)
p_load(gstat)
interpolate<-gstat::idw(Jan~1, samplestempsp, newdata=emptygrd, idp=2.0)
减。
ras<-raster(interpolate)%>%
  mask(.,Kenoutline)
plot(ras)
p_load(gstat)

interpolate<-gstat::idw(Jan~1, samplestempsp, newdata=emptygrd, idp=2.0)
ras<-raster(interpolate)%>%
  mask(.,Kenoutline)
plot(ras)
samplestemp<-samplestemp%>%
  st_transform(21097)
samplestemp
Kenoutline<-Kenoutline%>%
  st_transform(21097)



