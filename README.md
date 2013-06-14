Is that Citi Bike station dead? When were bikes shifted to that
station? When did station z go to 0 bikes or 0 docks?

This tracks the data in RRDtool.

0.  Install RRDtool.

1.  Run pollup once by hand ignoring the error.

2.  ```shell
    cut -d ' ' -f 1 grab | cut -c6-9 > id
    ```

3.  Edit file 'id' to remove the first two lines, and any stations you
    do not care about. The left columns in 'grab' are the only key.

4.  Run massrd.

5.  Have pollup run every minute from cron.

6.  Wait a few minutes.

7.  Run draw.

8.  Wait more.

9.  Go to 7.


