from picamera import PiCamera 
from time import sleep
from datetime import datetime
from orbit import ISS

cam = PiCamera()

location=ISS.coordinates()
lat = location.latitude.degrees
lon = location.longitude.degrees
print (location)

print(f"breddegrader:{location.latitude.degrees}")
print(f"længdegrader:{location.longitude.degrees}")

if location.latitude.degrees>0:
    print("nordlige halvkugle")
else:
    print("sydlige halvkugle")
    
    
def billed():
    nowtime = datetime.now()
    btid = nowtime.strftime("%H: %M: %S")
    
    cam.start_preview()
    if -7.83<lat and lat<-1.55 and -67.9<lon and lon<-58.4:
        for i in range(5):
            cam.annotate_text = str(btid)
            cam.capture('/home/pi/Tiger/image%s.jpg' %btid)
    else:
        print("intet billed")
    cam.stop_preview()
    
billed()
