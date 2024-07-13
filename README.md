import java.time.LocalTime;
import java.time.format.DateTimeFormatter;
import java.util.ArrayList;
import java.util.Arrays;
import java.util.List;

public class DailyReminderApp {
    public static void main(String[] args) {
        List<String> reminders = Arrays.asList("06:00", "07:00", "08:00", "10:00", "15:00");
        remindActivities(reminders);
    }

    public static void remindActivities(List<String> times) {
        DateTimeFormatter formatter = DateTimeFormatter.ofPattern("HH:mm");
        for (String timeStr : times) {
            try {
                LocalTime time = LocalTime.parse(timeStr, formatter);
                System.out.println("Reminder set for: " + time);
            } catch (Exception e) {
                System.out.println("Error parsing time: " + timeStr);
                e.printStackTrace();
            }
        }
    }
}
output
Reminder set for: 06:00
Reminder set for: 07:00
Reminder set for: 08:00
Reminder set for: 10:00
Reminder set for: 15:00
