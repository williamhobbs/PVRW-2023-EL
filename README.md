# EL with the Raspberry Pi Camera Module 3 - Supporting Files

This repo contains supporting files for the NREL PVRW 2023 poster, _EL with the Raspberry Pi Camera Module 3_, by Will Hobbs and Tim Silverman. 

Notes on setting up a live EL demo are in [live-demo-setup-notes.md](live-demo-setup-notes.md).

EL images used in the poster are in the [images](images) folder. Metadata for the images are in the table below.



| Image File | Camera | Exposure Time (s) | Gain | Note |
| --- | --- | --- | --- | --- |
| [picture_01c.jpg](images/picture_01c.jpg) | HQ | 1.5 | 6 | - |
| [picture_02a.jpg](images/picture_02a.jpg) | HQ | 1.0 | 7 | - |
| [picture_03.jpg](images/picture_03.jpg) | HQ | 0.5 | 8 | - |
| [picture_04.jpg](images/picture_04.jpg) | HQ | 0.1 | 16 | - |
| [picture_05.jpg](images/picture_05.jpg) | V3 | 1.5 | 6 | - |
| [picture_06.jpg](images/picture_06.jpg) | V3 | 1.0 | 7 | - |
| [picture_07.jpg](images/picture_07.jpg) | V3 | 0.5 | 8 | - |
| [picture_08.jpg](images/picture_08.jpg) | V3 | 1.0 | 16 | - |
| [picture_10.jpg](images/picture_10.jpg) | V3 | 1.5 | 6 | Frame edge |
| [picture_16.dng](images/picture_16.dng) | V3 | 1.5 | 2 | Raw .dng |
| [picture_16.jpg](images/picture_16.jpg) | V3 | 1.5 | 2 | .jpg accompanying the raw image |

Images were catured with commands like the following:

```bash
libcamera-still --awbgains 1,1 --gain 2 --shutter 1500000 -r -n -o picture_16.jpg
```

## Hardware used
### Filters
Filters similar to the following were used:
- https://www.newport.com/p/10CGA-1000 
- https://www.edmundoptics.com/p/1000nm-254mm-dia-colored-glass-replacement-longpass-filter/43198/

The live EL demo setup used the Newport 1000 nm filter, custom ordered in 49.0 mm diameter. The filter was placed inside of a standard 52 mm photoggraphy filter ring (https://www.amazon.com/AmazonBasics-UV-Protection-Lens-Filter/dp/B00XNMWCF8/) after disasembling the filter and removing the UV glass with a lens spanner tool (https://www.amazon.com/Neewer-Professional-pointed-Spanner-Repairing/dp/B00J5F6O92). 

### Case
The case used for the Pi Zero 2 W and camera was based on https://www.thingiverse.com/thing:2300226, modified to add support for a 52 mm filter. The Camera Module 3 did not fit in the case, and manual adjustments were needed after 3d printing the case, so I don't have a usable set of part files to share. 

### Modules
The live demo used:
- Newpowa 5W mono module, https://www.amazon.com/gp/product/B00L60Y6Y4/
- Voltaic P126, https://www.adafruit.com/product/5366
