# calculator
import java.util.Scanner;

public class Clander
{


    public int get_1st_weekday(int year){
        int d;
        d=(((year-1)*365 )+ ((year-1)/4) -((year-1)/100)+((year)/400) + 1) % 7;
        return d;
    }
    public static void main(String[] args) {
        
        Scanner scanner = new Scanner(System.in);
        Clander s1=new Clander();
        int year , month, day, daysInMonth, weekDay =0, startDay;

        System.out.println("Enter your desired year :");
        year = scanner.nextInt();

        String months[] = {"January", "February", "March", "April", "May", "June", "July", "August","September", "October", "November", "December"};
        int monthDays[] ={31,28,31,30,31,30,31,31,30,31,30,31};
        

        if((year%4==0 && year%100!=0) || year%400==0){

            monthDays[1]=29;
        }

        startDay = s1.get_1st_weekday(year);

        for(month=0;month<12;month++){

            daysInMonth=monthDays[month];
            System.out.println(" ");

            System.out.println("................." +months[month] + ".................");
            System.out.println(" Sun Mon Tue Wed Thurs Fri Sat ");

            for(weekDay=0; weekDay<startDay; weekDay++){
                 System.out.print("     ");
            }

            for(day=1;day<=daysInMonth; day++){
               
                System.out.print("  "+ day+" ");

            

               if(++weekDay>6){
                System.out.println("");
                weekDay=0;
               }

               startDay = weekDay;

            }

           


        }


    }
}
