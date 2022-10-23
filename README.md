### assignment3

In this assignment, you will build a database using the "pension_2014.csv". The name of the database is "pension2014". In this database, you will have four tables:
1. geotb(geoid:text, geoname:text) primary key: geoid
2. govtypetb(govtypeid:integer, govtypelabel:text) primary key: govtypeid
3. penitemtb(penitemid:integer, penitemlabel:text) primary key: penitemid
4. penvaluetb(geoid:text, govtypeid:integer, penitemid:integer, amount:integer) primary key: geoid, govtypeid, penitemid

##### Task 1

1. Create a context manager class "SQLServer" to handle all transactions to the database\
  For example, you definr the SQLServer class like this:
  
  ```
    class SQLServer:
        def __init__(self, server):
          self.server = server
         
        def __enter__(self):
          # connect to database
          # assign value to self.conn, self.cur
          
        def __exit__(self, exc_type, exc_val, exc_tb)
          self.conn.close()
  ```        
    
  And use your context manage like this:
  
  ```
    sqlcmd = "select * from geotb"
    with SQLServer('pension2014') as sqls:
      sqls.cur.execute(sqlcmd)
      for row in sqls.cur:
        print(row)
  ```

##### Task 2

1. Create four tables, load data to all tables using "pension_2014.csv".
2. Use SQL join to retrieve data from "geotb, govtypetb, penitemid, geoid" into a table having the same column as pension_2014.csv. 

##### Task 3

- Find out the following information and plot the result: 
    - Find the ratio of "Employee contributions" to "Total Contributions" of the "State and Local". Sort the results desendingly and present it as a bar plot, use the name of the state as the label for the x-axis, use "EM/Total" as the label for the y-axis, use "Employee/Total ratio" as the title of the plot.  
    
