# my-fabric-sample

Example of a supply chain management app for Hyperledger Fabric

**For UBP Blockchain Institute cadets use only**

Created by Team 1 - Johnny, Joshua M, Jarod, Pau

Prerequisites:

1. Make sure that Go (golang) is properly installed.

2. You have the fabric-samples repository cloned in your machine.

3. You have Postman installed.

Set-up instructions:

1. Clone this repository.

2. Replace files (or backup before replacing) on your fabric-samples/chaincode/fabcar/go and fabric-samples/fabcar directories with the ones inside this repository.

3. Open fabric-samples/fabcar in Terminal.

4. Type and press Enter: ./openScm.sh

5. Type and press Enter: node enrollAdmin.sh

6. Type and press Enter: node registerUser.sh

7. Type and press Enter: node rSupplier1.sh

8. Type and press Enter: node rOEM.sh

9. To test all functions, type and press Enter: node app_scm.sh

   <Port> is 3000.

10. To test as supplier1, open a new Terminal window, type and press Enter: node appSupplier1.sh

    <Port> is 3001.

    Note: supplier1 can only raise an invoice (number 3 below).

10. To test as OEM, open a new Terminal window, type and press Enter: node appOEM.sh

    <Port> is 3002.

    Note: OEM can only set that goods are received (number 4 below).

How to use:
	
1. Open Postman

2. To display all invoices, set it to GET, type localhost:<Port>/queryAllInvoice in the address bar and click Send.

3. To raise an invoice, set it to POST, go to Body tab, and tick x-www-form-urlencoded

   Type in the following keys: (one key per line, case-sensitive)

	     Key			Value (sample)
	
	invoiceNumber		INV002
	billedTo		Lenovo
	invoiceDate		2/9/2019
	invoiceAmount		50000
	itemDescription		any description here
	gr			no
	isPaid			no
	paidAmount		0
	repaid			no
	repaymentAmount		0

   Type localhost:<Port>/invoice in the address bar and click Send.

   Do number 2 to check if it worked.

4. To set that goods are received in an invoice, set it to PUT, go to Body tab, and tick x-www-form-urlencoded

   Type in the following keys: (one key per line, case-sensitive)

	     Key			Value (sample)
	
	invoiceNumber		INV002
	gr			yes

   Type localhost:<Port>/invoice in the address bar and click Send.

   Do number 2 to check if it worked.

5. To pay the supplier by bank, set it to PUT, go to Body tab, and tick x-www-form-urlencoded

   Type in the following keys: (one key per line, case-sensitive)

	     Key			Value (sample)
	
	invoiceNumber		INVxxx
	isPaid			yes
	paidAmount		49000 (this must be less than the invoiceAmount)

   Type localhost:<Port>/invoice in the address bar and click Send.

   Do number 2 to check if it worked.

6. To repay the bank by OEM, set it to PUT, go to Body tab, and tick x-www-form-urlencoded

   Type in the following keys: (one key per line, case-sensitive)

	     Key			Value (sample)
	
	invoiceNumber		INVxxx
	repaid			yes
	repaymentAmount		51000 (this must be greater than the paidAmount)

   Type localhost:<Port>/invoice in the address bar and click Send.

   Do number 2 to check if it worked.

------------------------------------------------

This repo is still in progress. For questions, contact Johnny via Slack/Messenger/email.

Thank you. :)
    

