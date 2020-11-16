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
### Coverage

### PITest

### Static Analysis