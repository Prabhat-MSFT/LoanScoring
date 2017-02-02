# LoanScoring
Demo of Loan Scoring App - Includes models from sample loan scoring data base and a Visual studio solution

STEPS to use the code sample - 

1) Configure one box operationalization set up of R Server using https://msdn.microsoft.com/en-us/microsoft-r/operationalize/configuration-initial. One box set up is simpler, though you can also try the enterprise set up.

2) use the IP of web node with port or the virual IP (in case of Load balancer) to update remote login credentials in Model/LoanScoring.R file. 

remoteLogin("http://[RSERVER IP]:12800", session = TRUE, diff = TRUE, commandline =  TRUE, prompt = "REMOTE_TECHREADY>>>", username       =     "", password = "")

3) Update SWAGGER_FILE_PATH token in Model/LoanScoring.R to store SWAGGER DOC in a local file system. SWAGGER document relevant to the solution is checked-in at the top level of the file as LoanPredict.json

4) Run Model/LoanScoring.R in R Studio. This will publish the required service to the R Server set up in step 1.

5) Connect VS to this github repository to pull the code locally. Build and run.

6) Alternatively you can regenerate the client code via AUTOREST from the created SWAGGER document - please review the instructions here https://msdn.microsoft.com/en-us/microsoft-r/operationalize/app-developer-get-started. You can update the generated client code in the VS solution for any update.

7) Code is connected to AZURE, you can publish it to a app service within your subscription. 
