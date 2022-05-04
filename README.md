# Datacamp_DataAnalystWithSQLServerTrack

## Course Name: Writing Functions and Stored Procedure in SQL Server
Learn how to do effective exploratory data analysis on temporal data, create scalar and table variables to store data, and learn how to execute date manipulation. 
This chapter will also cover the following SQL functions: DATEDIFF( ), DATENAME( ), DATEPART( ), CAST( ), CONVERT( ), GETDATE( ), and DATEADD( ).
### Dataset:
Trip Data:
  CREATE DATABASE tripdata;
  USE tripdata;
  CREATE TABLE YellowTripData (ID INT, VendorID INT, PickupDate DATETIME2, DropoffDate DATETIME2, PassengerCount INT, TripDistance FLOAT, RateCodeID INT, StoreFwdFlag    CHAR(1), PULocationID INT, DOLocationID INT, PaymentType INT, FareAmount FLOAT, FareExtra FLOAT, MTATax FLOAT, TipAmount FLOAT, TollAmount FLOAT, ImproveSurcharge      FLOAT, TotalAmount FLOAT);
   BULK INSERT YellowTripData FROM '/home/repl/Tripdata_sample-pipe.csv' WITH(FIELDTERMINATOR =',', ROWTERMINATOR = '|');
  
 Bike Share Data:
  CREATE DATABASE BikeShare;
  GO
  USE BikeShare;
  GO
  CREATE TABLE CapitalBikeShare (ID INT, Duration INT, StartDate DATETIME2(7), EndDate DATETIME2(7), StartStationNumber INT, StartStation VARCHAR(100),
  EndStationNumber INT, EndStation VARCHAR(100), BikeNumber VARCHAR(50), MemberType VARCHAR(50));
  GO
  BULK INSERT CapitalBikeShare FROM '/home/repl/BikeShare-pipe.csv' WITH(FIELDTERMINATOR =',', ROWTERMINATOR = '\n');
  GO
  CREATE TABLE [dbo].[RideSummary]([Date] [date] NOT NULL, [RideHours] [numeric](18, 0) NOT NULL);
  GO
  INSERT INTO [dbo].[RideSummary] (Date, RideHours)
  VALUES ('3/1/2018', 388)
  GO
