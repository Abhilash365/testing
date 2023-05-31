#include<stdio.h>
#include<stdlib.h>
#include<string.h>

#define MAX_TICKETS 120
#define size 5
#define MAX_SIZE 20

//to book a ticket
int ticketNumber;
struct Ticket {
    char name[50];
    int age[100];
    char boarding[500];
    char isCancelled;
    char destination[50];
    int date[3];
    int seatno;
};

struct TrainTicketSystem {
    struct Ticket tickets[MAX_TICKETS];
    int numTickets;
};


void bookTicket(struct TrainTicketSystem* system) {
    struct Ticket newTicket;
    newTicket.seatno = system->numTickets + 1;
    if(newTicket.seatno<MAX_TICKETS)
    {

    	printf("-----------------------------------------------------------------------------");	
	printf("\nTr.No\tName\t\t\tDestinations\t\tCharges\t\tTime\n");
	printf("-----------------------------------------------------------------------------");
	printf("\n10001\tIITBhubaneswar Express\tBhubaneswarto Cuttack    \tFare=180/-");
	printf("\n10001\tIITBhubaneswar Express\tBhubaneswar To Khurda    \tFare=150/-");
	printf("\n10001\tIITBhubaneswar Express\tBhubaneswar To Sompet   \tFare=260/-");
	printf("\n10001\tIITBhubaneswar Express\tBhubaneswar To Ichapuram\tFare=250/-");
	printf("\n10001\tIITBhubaneswar Express\tBhubaneswar To Brahampur  \tFare=225/-");
	printf("\n10001\tIITBhubaneswar Express\tBhubaneswar To Balugon    \tFare=200/-");
    printf("\n10001\tIITBhubaneswar Express\t BhubaneswarTo Chatrapur  \tFare=150/-");
    printf("\n");	

    printf("Enter your name: ");
    fgets(newTicket.name, sizeof(newTicket.name), stdin);
    newTicket.name[strcspn(newTicket.name, "\n")] = '\0';
   
    
        for (int i = 0; newTicket.name[i] != '\0'; i++) 
        {
        if (isalpha(newTicket.name[i])) ;
        else
        {
        printf("Name entered is wrong\n");
        printf("Enter the name only using alphabets:");
        scanf("%c",&newTicket.name);
        }
        }
    


    printf("enter your age: ");
    fgets(newTicket.age, sizeof(newTicket.age),stdin);
    newTicket.age[strcspn(newTicket.age,"\n")] = '\0';
    
    if(newTicket.age>1||newTicket.age<100);
    else
    {
      printf("The age entered is wrong\n");
      printf("Enter correct age:");
      scanf("%d",&newTicket.age);
    }


    printf("Enter the boarding station: ");
    fgets(newTicket.boarding, sizeof(newTicket.boarding), stdin);
    newTicket.boarding[strcspn(newTicket.boarding, "\n")] = '\0';

    printf("Enter the destination station: ");
    fgets(newTicket.destination, sizeof(newTicket.destination), stdin);
    newTicket.destination[strcspn(newTicket.destination, "\n")] = '\0';

    printf("Enter the date(dd/mm/yy) format: ");
    fgets(newTicket.date, sizeof(newTicket.date), stdin);
    newTicket.date[strcspn(newTicket.date, "\n")] = '\0';

    printf("Train number is : 10001\n");


    if(strcmp(newTicket.boarding,"Bhubaneswar")==0 && strcmp(newTicket.destination,"Cuttack")==0|| strcmp(newTicket.boarding,"Cuttack")==0 && strcmp(newTicket.destination,"Bhubaneswar")==0)
    {
        printf("Fare=180/-\n");
        printf("Ticket booked successfully!\n");
        printf("Your seat number is %d.\n", newTicket.seatno);
        printf("Your train number is:10001\n");
    }

    
    else if(strcmp(newTicket.boarding,"Bhubaneswar")==0 && strcmp(newTicket.destination,"Khurda")==0 || strcmp(newTicket.boarding,"Khurda")==0 && strcmp(newTicket.destination,"Bhubaneswar")==0)
    {
        printf("Fare=150/-\n");
        printf("Ticket booked successfully!\n");
        printf("Your seat number is %d.\n", newTicket.seatno);
        printf("Your train number is:10001\n");
    }

    else if(strcmp(newTicket.boarding,"Sompet")==0 && strcmp(newTicket.destination,"Bhubaneswar")==0||strcmp(newTicket.boarding,"Bhubaneswar")==0 && strcmp(newTicket.destination,"Sompet")==0)
    {
        printf("Fare=260/-\n");
        printf("Ticket booked successfully!\n");
        printf("Your seat number is %d.\n", newTicket.seatno);
        printf("Your train number is:10001\n");
    }


    
    else if(strcmp(newTicket.boarding,"Bhubaneswar")==0 && strcmp(newTicket.destination,"Ichapuram")||strcmp(newTicket.boarding,"Ichapuram")==0 && strcmp(newTicket.destination,"Bhubaneswar")==0)
    {
        printf("Fare=250/-\n");
        printf("Ticket booked successfully!\n");
        printf("Your seat number is %d.\n", newTicket.seatno);
        printf("Your train number is:10001\n");
    }

    
    else if(strcmp(newTicket.boarding,"Bhubaneswar")==0 && strcmp(newTicket.destination,"Brahampur")||strcmp(newTicket.boarding,"Brahampur")==0 && strcmp(newTicket.destination,"Bhubaneswar")==0)
    {
        printf("Fare=225/-\n");
        printf("Ticket booked successfully!\n");
        printf("Your seat number is %d.\n", newTicket.seatno);
        printf("Your train number is:10001\n");
    }

        
    else if(strcmp(newTicket.boarding,"Balugon")==0 && strcmp(newTicket.destination,"Bhubaneswar")||strcmp(newTicket.boarding,"Bhubaneswar")==0 && strcmp(newTicket.destination,"Balugon")==0)
    {
        printf("Fare=200/-\n");
        printf("Ticket booked successfully!\n");
        printf("Your seat number is %d.\n", newTicket.seatno);
        printf("Your train number is:10001\n");
    }

        
   else if(strcmp(newTicket.boarding,"Bhubaneswar")==0 && strcmp(newTicket.destination,"Chatrapur")||strcmp(newTicket.boarding,"Chatrapur")==0 && strcmp(newTicket.destination,"Bhubaneswar")==0)
   {
        printf("Fare=150/-\n");
        printf("Ticket booked successfully!\n");
        printf("Your seat number is %d.\n", newTicket.seatno);
        printf("Your train number is:10001\n");
   }

     else
    {
        printf("Sorry, Your Destination can't Be Reached\n");
    }
    }
    else
    {
        printf("The seats are filled!Your ticket is coming under waiting list");
    }

}



//to cancel ticket
void cancelTicket(struct TrainTicketSystem* system) {
    if (system->numTickets == 0) {
        printf("No tickets booked yet.\n");
        return;
    }
    
    printf("Enter the seat number to cancel (1-%d): ", system->numTickets);
    int seatno;
    scanf("%d", &seatno);
    getchar(); 
	struct Ticket* ticket = &system->tickets[seatno - 1];


    if (seatno < 1 || ticketNumber > system->numTickets) {
        printf("Invalid seat number.\n");
        return;
    }
	 else if(ticket->isCancelled==1)
	 {
	 printf("Ticket is already cancelled.\n");
	 }
	 else 
	{
    printf("Ticket cancellation successful!\n");
	ticket->isCancelled=1;
	return;
	}  
    
}

//to display train stations
void display()
{
    struct Ticket newTicket;
    	printf("-----------------------------------------------------------------------------");	
	printf("\nTr.No\tName\t\t\tDestinations\t\tCharges\t\tTime\n");
	printf("-----------------------------------------------------------------------------");
	printf("\n10001\tIITBhubaneswar Express\tBhubaneswarto Cuttack    \tFare=180/-");
	printf("\n10001\tIITBhubaneswar Express\tBhubaneswar To Khurda    \tFare=150/-");
	printf("\n10001\tIITBhubaneswar Express\tBhubaneswar To Sompet   \tFare=260/-");
	printf("\n10001\tIITBhubaneswar Express\tBhubaneswar To Ichapuram\tFare=250/-");
	printf("\n10001\tIITBhubaneswar Express\tBhubaneswar To Brahampur  \tFare=220/-");
	printf("\n10001\tIITBhubaneswar Express\tBhubaneswar To Balugon    \tFare=200/-");
    printf("\n10001\tIITBhubaneswar Express\t BhubaneswarTo Chatrapur  \tFare=150/-\n");	
    if(newTicket.seatno!=0)
    {
    printf("\nPassenger name\t\t\t Passenger age\n");
    for(newTicket.seatno;newTicket.seatno<MAX_TICKETS;newTicket.seatno++)
    {
        printf("%s\t\t",newTicket.name);
        printf("%s",newTicket.age);
    }
    }
    else
    {
        printf("There are no tickets booked yet!");
    }
}
    
	
int main()
{
    
    struct TrainTicketSystem ticketSystem;
    ticketSystem.numTickets = 0;

    while (1) {
        printf("\n==== Train Ticket Reservation System ====\n");
        printf("1. Book Ticket\n");
        printf("2. Cancel Ticket\n");
        printf("3. Display Tickets\n");
        printf("4. Exit\n");


        int choice;
        int passengers[120];
        int rec[120];
        printf("Enter your choice (1-5): ");
        scanf("%d", &choice);
        getchar();  // consume the newline character
        switch (choice) {
            case 1:
                bookTicket(&ticketSystem);
                break;

            case 2:
                cancelTicket(&ticketSystem);
                break;
        
            case 3:
                display();
                break;

            case 4:
                printf("Thank you for using the Train Ticket Reservation System!\n");
                exit(0);

            default:
                printf("Invalid choice. Please try again.\n");
                break;
        }
    }
}
