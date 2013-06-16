Is that Citi Bike station dead? When were bikes shifted from _that_
station? When did station _z_ go to 0 bikes or 0 docks?

This tracks the data in RRDtool.

![](https://raw.github.com/ra/leftern/master/s521.png)

(the largest station, called _8 Ave & W 31 St,_ just west of Penn
Station on the evening of 6/15/2013)

0.  Install RRDtool, perhaps.

1.  Set WD in pollup to something handy.

1.  Run pollup once by hand ignoring the error.

2.  ``` grep -v Planned grab | cut -d ' ' -f 1 | cut -c6-9 > id ```

3.  Edit file 'id' to remove any stations you
    do not care about. (Runs fine with all stations on any contemporary
    machine.) The left columns in 'grab' are the only key.

4.  Run massrrd.

5.  Have pollup run every minute from cron.

6.  Wait a few minutes.

7.  Run draw.

8.  Wait more.

9.  Go to 9.

If you recreate 'id' and new stations appear you'll see something like
— ERROR: opening 's241.rrd': No such file or directory — when you run
draw. Generate its RRD file by hand using the line from massrrd.




