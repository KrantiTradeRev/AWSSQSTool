# AWS SQS automation Tool
This tool authenticates an IAM user and then sends/receives message(s) to/from a queue. It is a maven based project and you need to add the following dependencies to your pom.xml file-

<!-- https://mvnrepository.com/artifact/com.amazonaws/aws-java-sdk -->
		<dependency>
			<groupId>com.amazonaws</groupId>
			<artifactId>aws-java-sdk</artifactId>
			<version>1.11.339</version>
		</dependency>
		<!-- https://mvnrepository.com/artifact/org.apache.poi/poi -->
		<dependency>
			<groupId>org.apache.poi</groupId>
			<artifactId>poi</artifactId>
			<version>3.17</version>
		</dependency>
		<!-- https://mvnrepository.com/artifact/org.apache.poi/poi-ooxml -->
		<dependency>
			<groupId>org.apache.poi</groupId>
			<artifactId>poi-ooxml</artifactId>
			<version>3.17</version>
		</dependency>
		<!-- https://mvnrepository.com/artifact/org.apache.poi/poi-ooxml-schemas -->
		<dependency>
			<groupId>org.apache.poi</groupId>
			<artifactId>poi-ooxml-schemas</artifactId>
			<version>3.17</version>
		</dependency>

The tool has four classes-
1) SQSSimpleJavaClient: The SQSSimpleJavaClient has all the logic to connect to AWS, authenticate user and send or receive messages to the queue.
2) SQSStub: This is the runnable class with main method in it.
3) CredentialProvider: It provides the credentials of the user and other values which is stored in properties file.
4) ExcelUtils: It provides us the logic to connect to the excel file where we would define all our test scenarios.

Properties file (SQS.properties):
It contains the following values-
- authCode
- secretCode
- queueURL
- region
- payloadFilePath
- queueNameToBeCreated

Excel file (SampleSQSPayload.xlxs):
This is the file which contains the scenarios in the form of payloads. It must have two columns, where the first one describes the scenario and the latter contains the payload. The file can have as many rows as the scenarios are, but, the first row is regarded as header and not read as input. Please note that the payload must follow a strict template and must always be entered in the second column.
