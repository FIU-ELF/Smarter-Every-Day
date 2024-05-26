# Smarter Every Day Satellites
Destin from "Smarter Ever Day" posted a video where he noticed two satellites photobomb his solar eclipse. This GH is an attempt to reverse engineer which satellites photobombed the images.

## Video Link

<a href="http://www.youtube.com/watch?feature=player_embedded&v=bQF51mqzrY4
" target="_blank"><img src="https://yt3.googleusercontent.com/ytc/AIdro_l59Ewmp0DHZBRWbY9dVqjd2_mWwvrn8ad0bJfmdbMRYcA=s160-c-k-c0x00ffffff-no-rj" 
alt="Smarter Every Day Video" width="240" height="180" border="10" /></a>

## Summary of Base Data from Video
### Location, Time & Date
Based on the video from Smarter Every Day:
1. The location is Jackson, Missouri (Drury Hotel: 37.42925803643183, -89.64323382671625) 
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
2. It then computes Azimuth and Elevation range for active satellites from Celestrak for the location and date/time window
3. It then compares to find satellites within a field of view of "specified" degrees. The script started with a rather wide field of view for the observation but we can downselect candidates after (like a sieve)
4. The video's observations are rather fast so the transit's duration is a bit ambigious. To confirm visuals, we'll plot a few minutes of time in our python ground plots.

The python script ran for 3 minutes after the solar eclipse's end (starts just before the end), which is more than enough time to catch a satellite near Baily's beads and one right after in the solar disk.

## Results and Comparison with Orbitron
Active satellites were loaded into the script but no results seemed plausible. A OneWeb satellite seemed close but didn't fit the time window.

This Orbitron plot shows active satellites. There are lot.

![alt text](https://github.com/FIU-ELF/Smarter-Every-Day/blob/main/Images/Orbitron.png "Orbitron radar view of satellites in Jackson, Missouri")

I then proceeded to try to get debris TLEs. Once, in Sanibel, I saw what I thought was a satellite. It turned out to be rocket debris. In fact, most "satellites" seen in space tend to be debris. Celestrak (Thank you Dr. Kelso for your service over they years) has deprecated various TLE sets because of user abuses. A catalog including debris was downloaded from Space-Track.org.

Visualised in Orbitron, the added density of objects when debris is included is seen:

![alt text](https://github.com/FIU-ELF/Smarter-Every-Day/blob/main/Images/Orbitron_debris.png "Orbitron radar view of satellites & debris in Jackson, Missouri")

This is where the script comes in handy. Running the script with a wide net of 10 degrees of field of view and outputting the relevent TLEs gives the result of:

![alt text](https://github.com/FIU-ELF/Smarter-Every-Day/blob/main/Images/sieved_radar.png "Orbitron radar view of sieved satellites & debris in Jackson, Missouri")

Further refining to 2 degrees of field of view gives us 4 satellites, of which 2 seem to fit the requirement of back to back passes, one at baily's beads and the other on the solar disk:

![alt text](https://github.com/FIU-ELF/Smarter-Every-Day/blob/main/Images/potential_solve.png "Orbitron radar view of sieved satellites & debris in Jackson, Missouri")

TLEs for this set can be found:






## Notes


