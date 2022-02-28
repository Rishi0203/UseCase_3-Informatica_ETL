<h1>SCD 2 Implementation using Informatica</h1>

<h3>Desciption </h3> 

<p>Here, client have given CustomerDetails (Source Table) and CUSTOMER_DETAIL_TRG (Target Table) and client requirement implement SCD 2 on User_Name and Credit_Score. So, i implemnted SCD 2 on User_Name and Credit_Score, so in future if User_Name and Credit_Score changed so its update and also save previous history data.</p>

<h3>Tables Desciption </h3>
<p><b>Table 1: CustomerDetails (Source Table) </b>- The customer table captures all customer details.</p>
<table>
  <tr>
    <th>Column Name</th>
    <th>Column Type</th>
  </tr>  
  <tr>
    <td>CusID</td>
    <td>FLOAT</td>
  </tr>
    <tr>
    <td>FNAME</td>
    <td>VARCHAR(20)</td>
  </tr>
    <tr>
    <td>MNAME</td>
    <td>VARCHAR(20)</td>
  </tr>
    <tr>
    <td>LNAME</td>
    <td>VARCHAR(20)</td>
  </tr>
    <tr>
    <td>ADDRESS</td>
    <td>VARCHAR(100)</td>
  </tr>
    <tr>
    <td>ORG_NAME</td>
    <td>VARCHAR(10)</td>
  </tr>
    <tr>
    <td>DESIGNATION</td>
    <td>VARCHAR(20)</td>
  </tr>
    <tr>
    <td>INCOME</td>
    <td>DECIMAL(7,2)</td>
  </tr>  
    <tr>
    <td>CREDIT_SCORE</td>
    <td>INT</td>
  </tr>  
    <tr>
    <td>APPLICATION_DATE</td>
    <td>DATETIME</td>
  </tr>
</table>

<p><b>Table 2: CUSTOMER_DETAIL_TRG (Target Table) </b>- The target customer table captures all customer details.</p>
<table>
  <tr>
    <th>Column Name</th>
    <th>Column Type</th>
  </tr>  
  <tr>
    <td>SK_ID</td>
    <td>NUMBER</td>
  </tr>
  <tr>
    <td>CuID</td>
    <td>NUMBER(38)</td>
  </tr>
    <tr>
    <td>FULLNAME</td>
    <td>VARCHAR2(40)</td>
  </tr>
    <tr>
    <td>ORG_NAME</td>
    <td>VARCHAR2(20)</td>
  </tr>
    <tr>
    <td>EMAIL</td>
    <td>VARCHAR2(20)</td>
  </tr>
    <tr>
    <td>INCOME</td>
    <td>NUMBER(7,2)</td>
  </tr>  
    <tr>
    <td>CREDIT_SCORE</td>
    <td>NUMBER</td>
  </tr>  
    <tr>
    <td>APPLICATION_DATE</td>
    <td>DATE</td>
  </tr>
    <tr>
    <td>DESIGNATION</td>
    <td>VARCHAR2(20)</td>
  </tr>  
</table>
<h4>Process load data from source to target table:</h4>
<ol>
  <li>First load table from source database to source designer and target database to target designer.</li>
  <li>Add mapping in informatica</li>
  <li>Convert source data types to informatica datatypes.</li>
  <li>Add Expression transformation for add some columns.</li>
  <li>Add lookup transformation on target table.</li>
  <li>Add Expression transformation for add some columns.</li>
  <li>Add Router transformation for divide data into insert and update groups.</li>
  <li>Add Sequence transformation for generate surrodate key for target table.</li>
  <li>Add Update strategy for insert and update records.</li>
  <li>Add target table into mapping.</li> 
  <li>Add Workflow and session for relevant mapping.</li>
  <li>Run particular workflow</li> 
<ol>
