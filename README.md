# Smarter Every Day Satellites
Destin from "Smarter Ever Day" posted a video where he noticed two satellites photobomb his solar eclipse. This GH is an attempt to reverse engineer which satellites photobombed the images.

## Video Link

<a href="http://www.youtube.com/watch?feature=player_embedded&v=bQF51mqzrY4
" target="_blank"><img src="https://yt3.googleusercontent.com/ytc/AIdro_l59Ewmp0DHZBRWbY9dVqjd2_mWwvrn8ad0bJfmdbMRYcA=s160-c-k-c0x00ffffff-no-rj" 
alt="Smarter Every Day Video" width="240" height="180" border="10" /></a>

## Summary of Base Data from Video
### Location, Time & Date
Based on the video from Smarter Every Day:
1. The location is Jackson, Missouri
2. The data is the solar eclipse, 4/8/2024
3. Duration of Totality*: 4m 9.6s
4. Totality Start*: 13:58:11 (CDT (GMT-5))
5. Mid-eclipse*: 14:00:16 (CDT (GMT-5))

### Obvervation
1. A satellite slightly away from Baily's beads
2. A satellite right after the previous one but on the solar disk

For a satellite to cause a flare during a solar eclipse, the satellite must be out of the shadow of the eclipse and the angle of light reflect from Sun to Satellite should be about the same as from Satellite to Observer.

## Python Script
This python script uses a TLE filed pulled from Celestrak and then:
1. Given a lat/lon and date/time range computes the Azimuth and Elevation to the sun
2. It then computes Azimuth and Elevation for active satellites from Celestrak for the location and date/time
3. It then compares to find satellites within a field of view of 5 degrees. This is a rather wide field of view for the observation but we can downselect candidates after
4. The time step is set to look every second. The video's observations are rather fast so the transit's duration is a bit ambigious

The python script computer for 3 minutes after the solar eclipse's end (starts just before), which is more than enough time to catch a satellite near Baily's beads.

## Results

## Comparison with Orbitron

![alt text](https://github.com/FIU-ELF/Smarter-Every-Day/blob/main/Images/Orbitron.png "Orbitron radar view of satellites in Jackson, Missouri")


## Notes


