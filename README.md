# myProjects
my projects
import java.io.*;
import java.util.*;

public class Solution {

    public static void main(String[] args) {
        /* Enter your code here. Read input from STDIN. Print output to STDOUT. Your class should be named Solution. */
        Scanner scan=new Scanner(System.in);
        int n;
        n=scan.nextInt();
        int k;
        k=scan.nextInt();
        
        Integer[] numbers=new Integer[n];
        Integer[] remainderCount=new Integer[k];
        Arrays.fill(remainderCount,0);
        for(int i=0;i<n;i++){
            numbers[i]=scan.nextInt();
            
        }
        
        
            for(int j=0;j<n;j++){
           
            int index=numbers[j] % k;
            remainderCount[index]=remainderCount[index]+1;
        
        }
        int count=0;
        if(remainderCount[0]>0)
            count=count+1;
       
        for(int i=1;i<=k/2;i++){
            if(remainderCount[i]>=remainderCount[k-i]){
                count=count+remainderCount[i];
                
            }
            else {
                count=count+remainderCount[k-i];
            }
        }
         if(k%2==0)
            count=count-remainderCount[k/2]+1;
        System.out.println(count);
    }
}
