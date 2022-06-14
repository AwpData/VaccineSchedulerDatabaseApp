# VaccineSchedulerDatabaseApp

A simulation of registering for a COVID-19 vaccine appointment. It already includes the 3 main vaccines (J&J, Pfizer, Moderna), but caregivers can create new ones. This project was created mainly to enchance my learning of database applications including using SQL in python with <a href="https://pythonhosted.org/pymssql/index.html">pymssql</a>, ER diagrams, data normalization, and SQL queries / updates.

<h2> Guide </h2>
<li> Once the user runs the program, they will be greeted with this menu. I will run through what each option does.
<pre>
Welcome to the COVID-19 Vaccine Reservation Scheduling Application!
 *** Please enter one of the following commands ***
> create_patient &ltusername> &ltpassword>
> create_caregiver &ltusername> &ltpassword>
> login_patient &ltusername> &ltpassword>
> login_caregiver &ltusername> &ltpassword>
> search_caregiver_schedule &ltdate>
> reserve &ltdate> &ltvaccine>
> upload_availability &ltdate>
> cancel &ltappointment_id>
> show_all_available_dates
> add_doses &ltvaccine> &ltnumber>
> get_vaccine_information
> show_appointments
> logout
> help (see this menu again)
> quit
</pre>

 <li><b>create_patient</b> and <b>create_caregiver</b> allows the user to create a patient to receive the vaccine or a caregiver to adminster it. Note that a caregiver does not require any medical license or degree as this is purely a simulation. Passwords are checked using Regex and then hashed using the SHA-256 algorithm if valid. 
 
 <li><b>login_patient</b> and <b>login_caregiver</b> allows the user to login as an existing patient and caregiver.
 
 <li><b>search_caregiver_schedule</b> allows a caregiver or patient to search for caregivers available on the given date as well as the number of doses of each vaccine left.

 <li><b>reserve</b> allows a patient to reserve a valid date and vaccine (assuming there are doses left) for an appointment with a caregiver that day. The caregiver is chosen in ascending alphabetical order. 
 
 <li><b>upload_availability</b> allows caregivers to upload a date when they are available for patients to make an appointment with them.
 
 <li><b>cancel</b> allows both patients and caregivers to cancel a valid date they have an appointment on.
  
 <li><b>show_all_available_dates</b> shows all available dates for every caregiver. 
 
 <li><b>add_doses</b> allows caregivers to add doses to existing vaccines or to create a new vaccine (real or fiction).
 
 <li><b>get_vaccine_information</b> displays all existing vaccines in the database with their number of doses remaining.
 
 <li><b>show_appointments</b> shows appointments for the logged in patient or caregiver
 
 <li><b>logout</b> is self-explanatory
 
 <li><b>help</b> displays the main menu again. Note that the menu will not print again after commands are entered so that information is not lost by the menu being printed a lot of times.
 
 <li><b>quit</b> terminates the program.
 
 <h2>Requirements / Installation</h2>
 <li>Clone the repo into an IDE
 <li>Create a database server (Microsoft Azure heavily recommended as it works well with pymssql).
 <li>Create an environment in <a href="https://www.anaconda.com/">Anaconda</a> while configuring the environment variables to connect to the database server
 <li>Run <code>scheduler.py</code> in Anaconda

<h2>Disclaimer</h2>
<li> This program is not affilated with any governmental program / agency and should not be taken seriously as a source of information related to COVID-19 or as medical advice. Please visit an official site such as <a href="https://www.vaccines.gov/">vaccines.gov</a> to schedule an actual appointment or seek verified medical advice.
