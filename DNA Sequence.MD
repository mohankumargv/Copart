
import java.util.Scanner;

class DNA1
{
	public int lengthOfLongestSubstring(String s, int result) {
        if(s==null)
            return 0;
	boolean[] flag = new boolean[256];
 
	result = 0;
	int start = 0;
	char[] arr = s.toCharArray();
 
	for (int i = 0; i < arr.length; i++) {
		char current = arr[i];
		if(current == 'A' || current == 'T'|| current == 'G' || current == 'C')
		{
		if (flag[current]) {
			result = Math.max(result, i - start);
			for (int k = start; k < i; k++) {
				if (arr[k] == current) {
					start = k + 1; 
					break;
				}
				flag[arr[k]] = false;
			}
		} else {
			flag[current] = true;
		}
		}
		else
		{
			System.out.println("Invalid Input");
			break;
		}
	}
 
	result = Math.max(arr.length - start, result);
    System.out.println(result);
	return result;
}
}
public class DNA
{
    public static void main(String[] args)
  {
DNA1 d=new DNA1();
      int result=0;
    String Input;
	System.out.println("Enter the String");
Scanner scanInput = new Scanner(System.in);
Input = scanInput.next);
scanInput.close();
d.lengthOfLongestSubstring(Input,result);


  }
}
