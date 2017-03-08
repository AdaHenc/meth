	public static void changeUserInfo
		int chosenId;

		System.out.println("\n-----------");
		System.out.println("CHANGE USER INFO");
		System.out.println("-----------");

		User.printUsernames();

		System.out.println("Which user's info would you like to change?" );

		while (true) {
			System.out.println("Enter ID of the user for which you want to change the information.");
			try {
				chosenId = userInputInt.nextInt();
				if( chosenId > ReadFile.getNumberOfUsers()){
					System.out.println("This is not a valid Id. Try again");
					continue; 
				} else break;
			}

			catch(InputMismatchException exception) {
				System.out.println("This is not a valid input.");
				continue;
			}
		}
		System.out.println("Do you want to change username(1) or passowrd(2)?" );
		int choiceInfoChange = userInputInt.nextInt();
		while(choiceInfoChange != 1 && choiceInfoChange != 2){
			System.out.println("Not a valid input. Enter 1 or 2.");
			choiceInfoChange = userInputInt.nextInt();
		}

		if(choiceInfoChange == 1){

			System.out.println("Please enter new username.");
			String newUserName = userInputString.nextLine();

			while(true){
				if(newUserName.equals("")){
					System.out.println("Can't be empty! Try again!");
					newUserName = userInputString.nextLine();
					continue;
				}
				System.out.println("Username changed. The new username is " + newUserName);
			}
		}

		else if(choiceInfoChange == 2){

			System.out.println("Please enter new password.");
			String newPassword = userInputString.nextLine();

			while(true){			
				while(true){

					if(newPassword.equals("")) {
						System.out.println("Can't be empty. Try again:");
						newPassword = userInputString.nextLine();
					}	else break;
				}

				System.out.print("Repeat new password: ");
				String repeatNewPassword = userInputString.nextLine();		
				if(repeatNewPassword.equals(newPassword)) break;			
				System.out.println("Your passwords don't match!");
			}

			System.out.println("Your password has been changed!");
		}

	}
