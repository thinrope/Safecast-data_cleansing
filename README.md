# Safecast-data_cleansing

Initially this started as https://github.com/Safecast/safecastapi/issues/202 but since it si not part of the api, I am moving it here.

There are few dataset currently collectively know as "The Safecast data" and there exists other data (mostly bGeigie drive logs) that has not been uploaded yet.

"The Safecast data" consists of the following (S3 backup Y/N, SD card backup Y/N):

    mobile: legacy drives dataset (3M points) moved from the old API (S3:n, SD:y)
    mobile: current set of drives, uploaded directly on the new API (S3:y, SD:?)
    fixed: various sensors (NetRAD, nGeigie, Onyx) (S3:n, SD:n)
    fixed/mobile: randomly submitted single measurements (S3:n, SD:n)
    mobile: possibly NOT submitted files and various backups (S3:n, SD:y)

The legacy data (and may be some later mobile data) is in various formats, some described here: https://docs.google.com/spreadsheets/d/16G7GKIQexqPVLOLnYrjZMZdvD_acctbj3opVLa57uEg I also should have notes from 2011-2012 when I was cleansing data for the Fusion map (http://gamma.tar.bz/maps/main/) and recovering lost data from buggy bGeigie classic units.

Some of the metadata (driver, comments, sensor height and orientation) will need to be matched to the database, some will need to be reworked manually.

Some drive logs can be easily matched (by hash) to the S3 backup and among various backups, but some have been hand-editted /split (hopefully not merged). Partial hashes, or line/block based hashes can be used.

Initial output will probably be spatiallite file as well as QGIS-2.10 project. Those will be (half-manually) updated, probably as change-sets every few months by someone (me=Kalin initially).

As a side product, some statistics and visualizations will be produced, hopefully a blogpost about it.

