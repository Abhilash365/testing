# TRAIN TICKEET BOOKING SYSTEM.
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

#define MAX_TICKETS 100

struct Ticket {
    int id;
    char name[50];
    char source[50];
    char destination[50];
    float fare;
    int status; // 1 for booked, 0 for cancelled
};

struct Ticket tickets[MAX_TICKETS];
int ticketCount = 0;

void bookTicket() {
    struct Ticket newTicket;
    
    printf("Enter passenger name: ");
    fgets(newTicket.name, sizeof(newTicket.name), stdin);
    
    printf("Enter source station: ");
    fgets(newTicket.source, sizeof(newTicket.source), stdin);
    
    printf("Enter destination station: ");
    fgets(newTicket.destination, sizeof(newTicket.destination), stdin);
    
    printf("Enter fare: ");
    scanf("%f", &newTicket.fare);
    
    newTicket.status = 1; // booked
    
    newTicket.id = ticketCount + 1; // generate a unique ID
    
    // Add the ticket to the array
    tickets[ticketCount] = newTicket;
    ticketCount++;
    
    printf("Ticket booked successfully. Ticket ID: %d\n", newTicket.id);
}

void cancelTicket() {
    int ticketId;
    printf("Enter ticket ID to cancel: ");
    scanf("%d", &ticketId);
    
    // Find the ticket with the given ID
    int i;
    for (i = 0; i < ticketCount; i++) {
        if (tickets[i].id == ticketId) {
            if (tickets[i].status == 0) {
                printf("Ticket is already cancelled.\n");
            } else {
                tickets[i].status = 0; // mark the ticket as cancelled
                printf("Ticket with ID %d has been cancelled.\n", ticketId);
            }
            return;
        }
    }
    
    printf("Ticket with ID %d not found.\n", ticketId);
}

void displayTicket(struct Ticket ticket) {
    printf("Ticket ID: %d\n", ticket.id);
    printf("Passenger Name: %s", ticket.name);
    printf("Source Station: %s", ticket.source);
    printf("Destination Station: %s", ticket.destination);
    printf("Fare: %.2f\n", ticket.fare);
    printf("Status: %s\n", ticket.status == 1 ? "Booked" : "Cancelled");
}

void displayAllTickets() {
    int i;
    for (i = 0; i < ticketCount; i++) {
        printf("------------\n");
        displayTicket(tickets[i]);
    }
}

int main() {
    int choice;
    
    do {
        printf("\nTrain Ticket Management System\n");
        printf("1. Book Ticket\n");
        printf("2. Cancel Ticket\n");
        printf("3. Display All Tickets\n");
        printf("4. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);
        
        switch (choice) {
            case 1:
                bookTicket();
                break;
            case 2:
                cancelTicket();
                break;
            case 3:
                displayAllTickets();
                break;
            case 4:
                printf("Exiting the program.\n");
                break;
            default:
                printf("Invalid choice. Please try again.\n");
        }
    } while (choice != 4);
    
    return 0;
}
