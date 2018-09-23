# Qlik-View
Part 1)


SET ThousandSep=',';
SET DecimalSep='.';
SET MoneyThousandSep=',';
SET MoneyDecimalSep='.';
SET MoneyFormat='$#,##0.00;($#,##0.00)';
SET TimeFormat='h:mm:ss TT';
SET DateFormat='M/D/YYYY';
SET TimestampFormat='M/D/YYYY h:mm:ss[.fff] TT';
SET MonthNames='Jan;Feb;Mar;Apr;May;Jun;Jul;Aug;Sep;Oct;Nov;Dec';
SET DayNames='Mon;Tue;Wed;Thu;Fri;Sat;Sun';
SET LongMonthNames='January;February;March;April;May;June;July;August;September;October;November;December';
SET LongDayNames='Monday;Tuesday;Wednesday;Thursday;Friday;Saturday;Sunday';
SET FirstWeekDay=6;
SET BrokenWeeks=1;
SET ReferenceDay=0;
SET FirstMonthOfYear=1;
SET CollationLocale='en-US';

OLEDB CONNECT32 TO [Provider=SQLOLEDB.1;Integrated Security=SSPI;Persist Security Info=False;Initial Catalog=Airbnb database;Data Source=DESKTOP-64367PF;Use Procedure for Prepare=1;Auto Translate=True;Packet Size=4096;Workstation ID=DESKTOP-64367PF;Use Encryption for Data=False;Tag with column collation when possible=False];
QUALIFY*;
UNQUALIFY Host_ID;
UNQUALIFY User_ID;
UNQUALIFY Property_ID;
UNQUALIFY Guest_ID;

LOAD "Property_ID",
    NoOfGuests,
    "Host_ID" as "HOST_ID",
    ZipCode,
    PricePerDay;
SQL SELECT *
FROM "Airbnb database".dbo.Property;

LOAD "Property_ID",
    "Guest_ID" as "User_ID",
    PropertyReview,
    HostReview;
SQL SELECT *
FROM "Airbnb database".dbo.Reviews;

LOAD "Property_Address",
    "Property_Zip",
    AptSuiteNo,
    "Property_ID";
SQL SELECT *
FROM "Airbnb database".dbo.PropLocation;

LOAD Wifi,
    "Heater_AC",
    Workspace,
    WasherDryer,
    Parking,
    Pool,
    Gym,
    "Property_ID";
SQL SELECT *
FROM "Airbnb database".dbo.PropAmenities;

LOAD "User_ID",
    "User_Type",
    "User_FName",
    "User_LName",
    "User_Phone",
    "User_Address",
    "User_Email",
    "User_SSN",
    "User_DrivingL",
    "User_DOB";
SQL SELECT *
FROM "Airbnb database".dbo."User";

LOAD "Property_ID",
    "Space_Details",
    "Guest_Bedrooms",
    "Guest_Bathrooms";
SQL SELECT *
FROM "Airbnb database".dbo.PropSpace;

LOAD Description,
    NoOfPhotos,
    "Property_ID",
    HouseRules;
SQL SELECT *
FROM "Airbnb database".dbo.PropDesc;

LOAD "Host_FName",
    "Host_LName",
    "Host_ID",
    "Host_LoginID",
    "Host_Password";
SQL SELECT *
FROM "Airbnb database".dbo.Host;

LOAD "Host_SSN",
    Status,
    "Host_DrivingL",
    "Host_ID";
SQL SELECT *
FROM "Airbnb database".dbo.BackgroundCheck;

LOAD "Booking_ID",
    "Host_ID",
    CheckIn,
    CheckOut,
    "Property_ID",
    "Total_Price",
    "Guest_ID";
SQL SELECT *
FROM "Airbnb database".dbo.BookingDetails;

LOAD "Guest_ID",
    "Guest_FName",
    "Guest_LName",
    "Guest_Login",
    "Guest_Password";
SQL SELECT *
FROM "Airbnb database".dbo.Guest;

LOAD "Guest_ID",
    NoOfGuests,
    CheckIn,
    CheckOut,
    "Property_Zip",
    MinPriceRange,
    MaxPriceRange,
    PropertyType,
    "Req_ID";
SQL SELECT *
FROM "Airbnb database".dbo.GuestRequirements;



Part 2)


SET ThousandSep=',';
SET DecimalSep='.';
SET MoneyThousandSep=',';
SET MoneyDecimalSep='.';
SET MoneyFormat='$#,##0.00;($#,##0.00)';
SET TimeFormat='h:mm:ss TT';
SET DateFormat='M/D/YYYY';
SET TimestampFormat='M/D/YYYY h:mm:ss[.fff] TT';
SET MonthNames='Jan;Feb;Mar;Apr;May;Jun;Jul;Aug;Sep;Oct;Nov;Dec';
SET DayNames='Mon;Tue;Wed;Thu;Fri;Sat;Sun';
SET LongMonthNames='January;February;March;April;May;June;July;August;September;October;November;December';
SET LongDayNames='Monday;Tuesday;Wednesday;Thursday;Friday;Saturday;Sunday';
SET FirstWeekDay=6;
SET BrokenWeeks=1;
SET ReferenceDay=0;
SET FirstMonthOfYear=1;
SET CollationLocale='en-US';

OLEDB CONNECT32 TO [Provider=SQLOLEDB.1;Integrated Security=SSPI;Persist Security Info=False;Initial Catalog=Airbnb database;Data Source=DESKTOP-64367PF;Use Procedure for Prepare=1;Auto Translate=True;Packet Size=4096;Workstation ID=DESKTOP-64367PF;Use Encryption for Data=False;Tag with column collation when possible=False];
QUALIFY*;
UNQUALIFY Host_ID;
UNQUALIFY User_ID;
UNQUALIFY Property_ID;
UNQUALIFY Guest_ID;

LOAD "Property_ID",
    NoOfGuests,
    "Host_ID" as "HOST_ID",
    ZipCode,
    PricePerDay;
SQL SELECT *
FROM "Airbnb database".dbo.Property;

LOAD "Property_ID",
    "Guest_ID" as "User_ID",
    PropertyReview,
    HostReview;
SQL SELECT *
FROM "Airbnb database".dbo.Reviews;

LOAD "Property_Address",
    "Property_Zip",
    AptSuiteNo,
    "Property_ID";
SQL SELECT *
FROM "Airbnb database".dbo.PropLocation;

LOAD Wifi,
    "Heater_AC",
    Workspace,
    WasherDryer,
    Parking,
    Pool,
    Gym,
    "Property_ID";
SQL SELECT *
FROM "Airbnb database".dbo.PropAmenities;

LOAD "User_ID",
    "User_Type",
    "User_FName",
    "User_LName",
    "User_Phone",
    "User_Address",
    "User_Email",
    "User_SSN",
    "User_DrivingL",
    "User_DOB";
SQL SELECT *
FROM "Airbnb database".dbo."User";

LOAD "Property_ID",
    "Space_Details",
    "Guest_Bedrooms",
    "Guest_Bathrooms";
SQL SELECT *
FROM "Airbnb database".dbo.PropSpace;

LOAD Description,
    NoOfPhotos,
    "Property_ID",
    HouseRules;
SQL SELECT *
FROM "Airbnb database".dbo.PropDesc;

LOAD "Host_FName",
    "Host_LName",
    "Host_ID",
    "Host_LoginID",
    "Host_Password";
SQL SELECT *
FROM "Airbnb database".dbo.Host;

LOAD "Host_SSN",
    Status,
    "Host_DrivingL",
    "Host_ID";
SQL SELECT *
FROM "Airbnb database".dbo.BackgroundCheck;

LOAD "Booking_ID",
    "Host_ID",
    CheckIn,
    CheckOut,
    "Property_ID",
    "Total_Price",
    "Guest_ID";
SQL SELECT *
FROM "Airbnb database".dbo.BookingDetails;

LOAD "Guest_ID",
    "Guest_FName",
    "Guest_LName",
    "Guest_Login",
    "Guest_Password";
SQL SELECT *
FROM "Airbnb database".dbo.Guest;

LOAD "Guest_ID",
    NoOfGuests,
    CheckIn,
    CheckOut,
    "Property_Zip",
    MinPriceRange,
    MaxPriceRange,
    PropertyType,
    "Req_ID";
SQL SELECT *
FROM "Airbnb database".dbo.GuestRequirements;
