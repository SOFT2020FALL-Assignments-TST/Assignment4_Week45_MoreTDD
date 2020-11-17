## Assignment4_Week45_MoreTDD  
**[Assignment Link](https://datsoftlyngby.github.io/soft2020fall/resources/672dd591-assignment-04.pdf)**

### Mockito powerups
**How do you verify that a mock was called?**  
@Mock SmsService smsSvc;  
String recipient = "+4511223344";  
when(smsSvc.sendSms(recipient.startWith("+45").thenReturn(true)));
**verify**(smsSvc.sendSms).sendSms(true);

**How do you verify that a mock was NOT called?**  
@Mock SmsService smsSvc;  
verify(smsSvc.**never()**).sendSms(true);

**How do you specify how many times a mock should have been called?**  
@Mock SmsService smsSvc;  
verify(smsSvc.**times(n)**).sendSms(true);

**How do you verify that a mock was called with specific arguments?**  
@Mock SmsService smsSvc;  
String recipient = "+4511223344";  
when(smsSvc.sendSms(**eq("+4511223344)**.thenReturn(true)));
verify(smsSvc.sendSms).sendSms(true);

**How do you use a predicate to verify the properties of the arguments
given to a call to the mock?**  
@Mock SmsService smsSvc;  
String recipient = "+4511223344";  
when(smsSvc.sendSms(**anyString()**.thenReturn(true)));  
verify(smsSvc.sendSms).sendSms(true);
***
### Maven Profiles
**With unit tests**  
mvn test -P with-unit-tests

**No unit tests**  
mvn test -P no-unit-tests

**Coverage**  
mvn test -P coverage

**PITest**  
mvn test -P pitest
***
### Coverage Report
JaCoCo  
*See profile **coverage** in pom.xml*
***
### Mutation Testing
PITest  
*See profile **pitest** in pom.xml*
***
### Static Analysis
Sonar  

**pom.xml** (inside **build** tag)  
pluginManagement  
    plugins  
        plugin  
            groupId org.sonarsource.scanner.maven groupId  
            artifactId sonar-maven-plugin artifactId  
            version 3.4.0.905 version  
        plugin  
    plugins  
pluginManagement  

**SonarQube community server**  
https://docs.sonarqube.org/latest/setup/get-started-2-minutes/

1. [Download](https://www.sonarqube.org/downloads/) the SonarQube Community Edition zip file.
2. As a non-root user, unzip it.
3. As a non-root user, start the SonarQube Server - see how below.
4. Log in to http://localhost:9000 using (login=admin, password=admin).

**windows**:  
%unzipped folder path%\bin\windows-x86-64\StartSonar.bat

**linux**:  
%unzipped folder path%/bin/**OS**/sonar.sh console

*If your instance fails to start, check your logs to find the cause.*

**Maven**  
mvn sonar:sonar -Dsonar.host.url=http://localhost:9000
***

