# tempyx

Bare bones jupyter alternative for finding and tracking lows in healpix data, to avoid having to export to netcdf and use tempestExtremes (etc).

It's very rough - needs some love from someone who knows weather systems - but the underlying algorithm seems to be pretty quick.

The strategy is to first locate local minima in presure, which can be done quickly in healpix.  Then apply filters to just these points.

The detection and tracking is all done in healpix pixels.  You convert to lat/lon at the end.

The way I've done it is to detect and track at low zooms and then analyse at high zooms.  You can then adjust the track using the hi res data if necessary.  It should also work for detection straight at high zoom.  Unsure which way would be quicker.

![image](https://github.com/user-attachments/assets/c6a973d4-1a03-44c5-aa14-a9deeb3b95f2)
