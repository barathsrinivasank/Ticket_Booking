# Ticket_Booking
import java.util.Scanner;

public class MovieBooking {

    public static void main(String[] args) {
        int[] seats = new int[10];
        int[] seats2 = new int[10];

        Scanner scanner = new Scanner(System.in);
        String userName;
        char userGender;

        for (int i = 0; i < 100; i++) {
            System.out.print("\nEnter your name: ");
            userName = scanner.nextLine();

            System.out.print("Enter your gender (M/F): ");
            userGender = scanner.next().charAt(0);

            System.out.println("\nSelect a movie:");
            System.out.println("1. Jigarthanda");
            System.out.println("2. Parking");
            System.out.print("Enter the number of the movie: ");
            int movieChoice = scanner.nextInt();

            switch (movieChoice) {
                case 1:
                    System.out.println("Enjoy watching Jigarthanda!");
                    System.out.print("Available Seats: ");
                    for (int j = 0; j < 10; j++) {
                        if (seats[j] == 0) {
                            System.out.print((j + 1) + " ");
                        }
                    }
                    System.out.print("\nEnter the seat number you want to book (1-10): ");
                    int seatChoice = scanner.nextInt();
                    if (seatChoice < 1 || seatChoice > 10 || seats[seatChoice - 1] == 1) {
                        System.out.println("Invalid seat choice or seat already booked. Exiting.");
                        continue;
                    }
                    seats[seatChoice - 1] = 1;
                    System.out.println();
                    System.out.println(userName);
                    System.out.println(userGender);
                    System.out.println("Seat " + seatChoice + " booked successfully!");
                    break;

                case 2:
                    System.out.println("Enjoy watching Parking!");
                    System.out.print("Available Seats: ");
                    for (int j = 0; j < 10; j++) {
                        if (seats2[j] == 0) {
                            System.out.print((j + 1) + " ");
                        }
                    }
                    System.out.print("\nEnter the seat number you want to book (1-10): ");
                    int seatChoice2 = scanner.nextInt();
                    if (seatChoice2 < 1 || seatChoice2 > 10 || seats2[seatChoice2 - 1] == 1) {
                        System.out.println("Invalid seat choice or seat already booked. Exiting.");
                        continue;
                    }
                    seats2[seatChoice2 - 1] = 1;
                    System.out.println();
                    System.out.println(userName);
                    System.out.println(userGender);
                    System.out.println("Seat " + seatChoice2 + " booked successfully!");
                    break;

                default:
                    System.out.println("Invalid movie choice.");
                    continue;
            }
        }

        scanner.close();
    }
}
