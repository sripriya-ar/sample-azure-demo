# sample-azure-demo

## Description
This project demostrates an implmentation of simple outer join of two databases on Azure cloud.

## Azure components and Setup

The following Azure data factory rsources are used to implement the project. 

###  Datasets using **Blob Storage**
Two CSV files stored in Azure blob stroage inside a container act as database inputs. The output is stored as a *paraquet* file.

 - geolocation

    This input csv file contains zipcode, latitude, longitude , city and state columns.
    
 - seller

    This  input csv file contains ID, zipcode, city and state columns.

- finaloutput

    This parquet file contains the output of the outer join performed.

## Dataflow 
A dataflow  named *dataflow1* contains the following factory resources.

 1. Source 

 Two source components -
  *seller* and *geolocation* tables are used as the source components in this data flow

 2. Join

 An outer join component *join1* perfoms the full outer join operations of the *Sources* using the column *zipcode* , and directs the output to sink component named *Sink*

 3. Sink

 A sink component named *sink1* contains the output of the outer join stored in parquet format.


## Result
The Parquet file named *finaloutput.parquet* contains the results of the outer join of both the tables.
