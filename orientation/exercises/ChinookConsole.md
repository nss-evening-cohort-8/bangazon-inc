Create a console application that allows the user to run and view the results of the following queries: 

1. Provide a query that shows the invoices associated with each sales agent. The resultant table should include the Sales Agent's full name.
1. Provide a query that shows the Invoice Total, Customer name, Country and Sale Agent name for all invoices.
1. Looking at the InvoiceLine table, provide a query that COUNTs the number of line items for an Invoice with a parameterized Id from user input
    
    - hint, this will use `ExecuteScalar`

1. INSERT a new invoice with parameters for customerid and billing address
1. UPDATE an Employee's name with a parameter for Employee Id and new name

Each query should be represented by a main menu item.  Each parameter should be prompted for by name from the user.

Remember, it is helpful to create models for these sets of data so that you have a way to represent them in your code.  Models do not have to be exactly representative of tables, but can also represent the results of queries.
