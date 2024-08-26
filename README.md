<h2>Scenario</h2>
<p>As a security professional at a large organization, your role includes investigating security issues to ensure system safety. Recently, you've identified potential security concerns related to login attempts and employee machines.</p>

<p>Your assignment involves analyzing the organization's data within the employees and log_in_attempts tables. You’ll need to apply SQL filters to extract records from different datasets and explore potential security concerns.</p>

<h3>Solution</h3>
<b>Step 1: <br>Extracting failed login attempts outside of regular hours.</b><br>
   The organization database contains the following tables: <u list-style-type="none"><li>log_in_attempts</i> <li>employees</i></u>
   <p>
   <pre>The <b>'log_in_attempts'</b> table has the following columns</pre>
    <ul>
    <li><b>event_id:</b> The unique identification number assigned to each login event.</li>
    <li><b>username:</b> The employee's username.</li>
    <li><b>login_date:</b> The date the login attempt was logged.</li>
    <li><b>login_time:</b> The time the login attempt was logged.</li>
    <li><b>country:</b> The country where the login attempt occurred.</li>
    <li><b>ip_address:</b> The IP address of that employee’s machine.</li>
    <li><b>success:</b> The success of the login attempt; FALSE (0) indicates a failed attempt.</li>
    </ul>

The login attempt time is recorded in the login_time column, while the success column indicates a failure with a value of 0 and a success with a value of 1.
</p>
<p>
   <pre>The <b>'employees'</b> table has the following columns</pre>
    <ul>
      <li><b>employee_id:</b> The unique identification number assigned to each employee.</li>
      <li><b>device_id:</b> The unique ID assigned to each device used by the employee.</li>
      <li><b>username:</b> The employee's username.</li>
      <li><b>department:</b> The employee's department.</li>
      <li><b>office:</b> The office the employee is located in.</li>
    </ul>
</p>
<p>
 Assuming that, like most large organizations, this one closes at 18:00, I will use the following SQL filters to craft a query that identifies all failed login attempts occurring after 18:00:
<ul>
  <li>WHERE</li>
  <li>AND</li>
</ul><p>
<img width="854" alt="bukolasehinde-SQL1" src="https://github.com/user-attachments/assets/452fd7ef-e8c3-4d45-b1f6-d90454f814c0">


</p>
</p>

-------------------------------------------------------------------------------------------------------------------------
<b>Step 2: <br>Extracting login attempts from specific dates</b>
<h4>Sub-Scenario</h4> 
<p>A suspicious event took place on 2022-05-09. To investigate, we need to review all login attempts from that day and the previous day.<br> The login attempt date is recorded in the <b>login_date column</b>. I'll apply the following SQL filters to create a query that captures all login attempts from 2022-05-09 or 2022-05-08:
   
<ul>
  <li>WHERE</li>
  <li>OR</li>
</ul><p>
<img width="856" alt="bukolasehinde-SQL2" src="https://github.com/user-attachments/assets/4bdab022-be7f-49e0-987e-5c1a171e0672">
</p>
</p>

----------------------------------------------------------------------------------------------------------------------------
<b>Step 3: <br>Extracting login attempts outside of Mexico</b>
<h4>Sub-Scenario</h4> 
<p>Suspicious login activity has been detected, but the team has determined that it did not originate from Mexico. We now need to examine login attempts from locations outside Mexico (i.e., excluding country values of both MEX and MEXICO). 
I will apply the following SQL filters to create a query that identifies all login attempts occurring outside of Mexico:
<ul>
  <li>WHERE</li>
  <li>NOT</li>
  <li>LIKE</li>
  <li>A wildcard(%) to make sure the query reflects the country values 'MEX' and 'MEXICO'.</li>
</ul><p>
<img width="866" alt="bukolasehinde-SQL3" src="https://github.com/user-attachments/assets/af5c03f9-9af5-478e-94bd-60a6a60f820b">


</p>
</p>

----------------------------------------------------------------------------------------------------------------------------
<b>Step 4: <br>Extracting employee details in Marketing</b>
<h4>Sub-Scenario</h4> 
<p>
The security team needs to perform updates on specific employee machines in the Marketing department. You are tasked with gathering information about these machines by querying the employees table. The employee's department is listed in the <b>department</b> column, which includes values like Marketing, while the office location is specified in the <b>office</b> column with examples such as East-170, East-320, and North-434.
I will apply the following SQL filters to craft a query that identifies all employees in the Marketing department who are based in any of the East building offices:
<ul>
  <li>WHERE</li>
  <li>AND</li>
  <li>LIKE</li>
   <li>LIKE and % (To filter for the East building.)</li>
</ul>
<img width="453" alt="bukolasehinde-SQL4" src="https://github.com/user-attachments/assets/8819f176-2e40-4bd3-8dbe-b913364762aa">

</p>
</p>

----------------------------------------------------------------------------------------------------------------------------
<b>Step 5: <br>Extracting employee details in Finance or Sales</b>
<h4>Sub-Scenario</h4> 
<p>
The security team now requires a separate security update for machines used by employees in the Sales and Finance departments. The department information is found in the <b>department</b> column, which includes Sales and Finance.
   
I will apply the following SQL filters to create a query that identifies all employees in either the Sales or Finance departments:
<ul>
  <li>WHERE</li>
  <li>OR</li>
</ul><p>
<img width="720" alt="bukolasehinde-SQL5" src="https://github.com/user-attachments/assets/f629ec5e-ef7a-4f57-9a44-c8fe365b3e0b">

</p>
</p>

----------------------------------------------------------------------------------------------------------------------------
<b>Step 6: <br>Extracting all employee data not in IT</b>
<h4>Sub-Scenario</h4> 
<p>The security team needs to perform one final update on employee machines. While employees in the Information Technology department have already received this update, it is still required for employees in all other departments. The employee's department is listed in the <b>department</b> column, which includes Information Technology.

I will apply the following SQL filters to generate a query that identifies all employees who are not in the IT department:
<ul>
  <li>WHERE</li>
  <li>NOT</li>
</ul><p>
<img width="780" alt="bukolasehinde-SQL6" src="https://github.com/user-attachments/assets/b3d9f875-b350-4890-8fc1-deb05c10ddc9">

</p>
</p>

-----------------------------------------------------------------------------------------------------------------------------
<b>Summary:</b>
<p>
As a security professional, I have effectively retrieved after-hours failed login attempts, login attempts on specific dates, and those from outside Mexico, as well as employee data from various departments. By examining the organization’s data with SQL filters, I have successfully extracted records from different datasets and investigated potential security issues.
</p>
