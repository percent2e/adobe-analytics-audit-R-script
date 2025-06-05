# adobe-analytics-audit-R-script

R script to pull configuration data and sample values from Adobe Analytics.

This is based on Tim Wilson's version, which is based on Randy Zwitch's original script. 

This script pulls data from one or multiple report suites -- both the configuration
of the props, eVars, and events, as well as top values for the most recent 30 days,
and puts it into an Excel file -- one file for each report suite. 

This was an outgrowth
of a basic script that Randy Zwitch developed and is posted here:
http://www.r-bloggers.com/adobe-analytics-implementation-documentation-in-60-seconds/.

This script simply takes that script and: 

1) does some text cleanup to try to get the output to more closely mirror the values 
in the Admin Console of Adobe Analytics, and

2) it pulls actual data for events, eVars, and sProps so that a user can scan through
and see which ones are populated and what values they're being populated with.

The file is set up to loop through one RSID at a time because it can take up
to 20 minutes to do a single report suite. So, trying to do multiple in 
parallel seems like a long time to wait... especially if something craps out!
The script does return a warning, and I sort of know what's causing that, but
I haven't been able to address it yet. It doesn't actually affect the output.

Instructions (WIP):

1. Install R and R extension in Visual Studio Code
2. Open repo in Visual Studio Code
3. Access Adobe Analytics Web Services user name and Web Services secret from Adobe Analytics classic admin console
4. Add Web Services user name and secret to line 37 in AdobeAuditDocBuilder.R
5. Add the intended RSID to line 49 in the AdobeAuditDocBuilder.R
6. Open R terminal in Visual Studio Code (Cmd/Ctrl Shift P), then type "R: Create R Terminal"
7. Highlight R code and hit Cmd/Ctrl Enter to run R code
