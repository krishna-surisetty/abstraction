# Abstraction


Abstraction is process of hiding internal details of application from the outer world. It is used to create a boundary between application and client programs


# A real life example

Consider the laptop or computer you are working with. 

It starts when you click the power button. The keyboard letters you type on type on while be shown on screen

We don't know the actual process of what happens when we are clicking or typing internally on how the press of the button generates an electric pulse which is read by the processor to read or hardware interactions of components inside

It can be said that this implementation is abstracted from us

# Abstraction in OOP

A class as a blueprint defines what fields and methods it has. Not every method or logic that is used in implementing a method or a field need to known to other classes.
To achieve this we use access modifiers using which we can provide access only to necessary methods or fields that are required for other classes


# Abstraction Types

1. Data Abstraction

		class PersonalDetails {
		
			public String personName;
			public String gender;
			private String personAadharNumber;
			
			public String getPersonAadharNumber() {
				return personAadharNumber;
			}
			public void setPersonAadharNumber(String personAadharNumber) {
				this.personAadharNumber = personAadharNumber;
			}
		}


Here name and gender can be accessed by other class directly, but if they want to access the aadhar number they have to call the methods to get it

2. Process Abstraction


		class VerificationProcess {
		
			public String verificationResult;
			
			public String doVerification(PersonalDetails personalDetails) {
				// Some normal process to check the person information which 				// return Good or Bad
				secretProcessOfVerification(personalDetails);
				// If both are Good then return verified else Not verified
				return result;
			} 
			private String secretProcessOfVerification(PersonalDetails personalDetails) {
				 // Some complicated secret process which returns Good and Bad
		   }
		
		}
		
Here we have a class which does some person's verification. For the verification process to trigger the method doVerification() with person's details have to passed

The person should not know how the verification is done. Here we are doing some normal verification and getting the result of that and someProcessVerification() which no one should know and getting the result. Based on both results we are sending final verification status


