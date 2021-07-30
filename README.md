# Abstraction


Abstraction is process of hiding internal details of application from the outer world. It is used to create a boundary between application and client programs


# A real life example

Consider the laptop or computer you are working with. 

It starts when you click the power button. 
The letters on keyboard when we click(type) while be shown on screen

We don't know the actual process of what happens when we are clicking or typing internally on how the press of the button generates an electric pulse which is read by the processor to read or hardware interactions of components inside

It can be said that this implementation is abstracted from us

# Abstraction in OOP

A class as a blueprint defines, what fields and methods it has. Not every method or logic that is used in implementing a method or a field need to be known to other classes.
To achieve this we use interfaces and abstract classes usually

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
	
		Verification verification;
	
		public String doVerification(PersonalDetails personalDetails) {
		
		doBasicVerification(personalDetails)// Some normal process to check the person information which return Good or Bad
		verification.secretProcessOfVerification(personalDetails);
		// If both are Good then return verified else Not verified
		return result;
		} 
	
		public boolean doBasicVerification(PersonalDetails personalDetails) {
		// Some implementation for verification process step one
		return ;
			}
	   }


	
	   interface Verification {
			String secretProcessOfVerification(PersonalDetails personalDetails);
	   }

	


	   class VerificationImpl implements Verification {
		@Override
		public String secretProcessOfVerification(PersonalDetails personalDetails) {
		 	// Some complicated secret process which returns Good and Bad
		return "";
 	  		}
	   }
		
Here we have a class which does some person's verification. For the verification process to trigger the method doVerification() with person's details have to passed

The person should not know how the verification is done. Here we are doing some normal verification and getting the result of that and secretProcessOfVerification() which no one should know how is is done. Based on both results we are sending final verification status.

Notice that we used interface to obtain abstraction. We can also use an abstract class. Even for the doVerification() method we can create either interface or abstract class and make VerificationProcess class implement it


