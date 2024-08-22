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
<img width="960" alt="image" src="https://github.com/devhalimah/Google-Cybersecurity-Professional-Certificate-Projects/assets/64546668/38fb488f-321e-4edc-948b-6579bc03666f">
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
<img width="960" alt="image" src="https://github.com/devhalimah/Google-Cybersecurity-Professional-Certificate-Projects/assets/64546668/c7083ea7-a423-4a99-be0d-225672fb80a0">
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
<img width="960" alt="image" src="https://github.com/devhalimah/Google-Cybersecurity-Professional-Certificate-Projects/assets/64546668/9f2d6a32-c0e2-471f-bced-48dcf343b4a6">
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
<img width="483" alt="image" src="https://github.com/devhalimah/Google-Cybersecurity-Professional-Certificate-Projects/assets/64546668/4c030173-314c-48d4-b600-54b3ea026ada">
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
<img width="960" alt="image" src="https://github.com/devhalimah/Google-Cybersecurity-Professional-Certificate-Projects/assets/64546668/eb21e90c-913b-4def-b303-bfe6d636a5ae">
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
<img width="960" alt="image" src="https://github.com/devhalimah/Google-Cybersecurity-Professional-Certificate-Projects/assets/64546668/fd0a4bb6-fec7-49a0-9a8e-be5624d26695">
</p>
</p>

-----------------------------------------------------------------------------------------------------------------------------
<b>Summary:</b>
<p>
As a security professional, I have effectively retrieved after-hours failed login attempts, login attempts on specific dates, and those from outside Mexico, as well as employee data from various departments. By examining the organization’s data with SQL filters, I have successfully extracted records from different datasets and investigated potential security issues.
</p>
