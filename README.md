# PowerAutomateWorkshop
KP-Dagen
Step-by-Step Guide to Trigger a Flow on a Random Date
Create a Scheduled Flow:

Log in to Power Automate and create a new Scheduled cloud flow.
Set the schedule to run daily (or at a frequency that suits your needs).
Initialize Variables:

Add an Initialize variable action to store the current date.
Name: CurrentDate
Type: String
Value: formatDateTime(utcNow(), 'yyyy-MM-dd')
Add another Initialize variable action to store a random day of the month.
Name: RandomDay
Type: Integer
Value: rand(1, 28) (assuming you want a random day between 1 and 28)
Condition to Check the Random Date:

Add a Condition action to check if the current day matches the random day.
Condition: dayOfMonth(utcNow()) is equal to variables('RandomDay')
Add Actions Based on Your Needs:

In the If yes branch of the condition, add the actions you want to perform on the random date.
For example, you can send an email, post a message in Teams, or trigger another process.
Save and Test Your Flow:

Save your flow.
Test it to ensure it runs daily and performs the actions only on the random date.
Example Flow
Trigger: Recurrence (daily)
Action: Initialize variable CurrentDate
Action: Initialize variable RandomDay
Condition: Check if dayOfMonth(utcNow()) equals variables('RandomDay')
If yes: Add your desired actions (e.g., send an email)
