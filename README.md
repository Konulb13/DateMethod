# DateMethod
exam answer
import java.time.LocalDate;
import java.time.format.DateTimeFormatter;

public class secondTry {
	public static void printBonusDatesBetween(int fromYear, int toYear) {
		while (fromYear < toYear) {
			int YYYYlen = 4;
			String fromYearS = String.valueOf(fromYear); System.out.println(fromYear);
			int numOfZerosToInsert = YYYYlen - fromYearS.length();
			fromYearS = "0".repeat(numOfZerosToInsert) + fromYearS;
			
	  	// 	reverse the year to get MMdd
			char[] revDate = new char[fromYearS.length()];
			for (int i = 0; i < fromYearS.length(); i++) {
			  revDate[i] = fromYearS.charAt(fromYearS.length() - i - 1);
			}
			
			// join, current format: yyyyMMdd
			String fullDateStr = fromYearS + new String(revDate);
			
			try {
			  // if parse of date string succeeds, it is correct date, therefore print it out
        LocalDate a = LocalDate.parse(fullDateStr, DateTimeFormatter.BASIC_ISO_DATE);
        System.out.println(a);
      } catch (Exception e) {
        // pass
      }
      
			fromYear++;
		}
	}
	public static void main(String[] args) {
		printBonusDatesBetween(2010, 2015);
	}
}




