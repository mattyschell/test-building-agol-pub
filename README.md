# test-building-agol-pub

We will test the FME® (ETL from Safe Software http://www.safe.com) workspace that publishes New York City building footprints to ArcGIS Online.  Friends, this our test of an FME workspace, our rules, the trick is never to be afraid.

## Dependencies

1. Python 3 
2. FME Desktop
3. A read/write ESRI "sde" connection in SDE_Connections

## Run Tests
```
TBD
```

## Details

1. Start with a test set of building footprints
2. Load the test set to an ESRI Enterprise Geodatabase
3. Perform an edit on the test data
4. Run the FME workspace BUILDING_AGOL_FileGDB_Update.fmw
5. Assert that the FME workspace identifies the edit in step 3

## Even More Details

The BUILDING_AGOL_FileGDB_Update.fmw outputs

\Data\AgolFileGdbs\BUILDING\
    cb7726b6-c956-4186-b460-aa10f8c59d5a.gdb
        BUILDING

Where the BUILDING feature class is maintained as a mirrored copy of the public ArcGIS Online data.  We will put a feature class TEST_BUILDING in the file geodatabase as our test set and load this to an Enterprise Geodatabase.

The BUILDING_AGOL_FileGDB_Update.fmw also outputs 

\Data\AgolFileGdbs\BUILDING\
    BUILDING_CHANGES.gdb
        BUILDING_DELETED
        BUILDING_UPDATED_CHANGES

We will assert expected outputs appear in this feature class and table, respectively.

