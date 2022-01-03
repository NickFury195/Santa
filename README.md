
import java.io.*;
import java.util.*;


/* Copyright Act 1957 section 13 - All Rights Reserved
 * You may use, distribute and modify this code under the
 * terms of the santa private ltd license, which unfortunately won't be
 * written for another century.
 * @author Santanu Sarkar
 * @version 2.1.2022
 */


public class Search
{
    public static void main(String []args)throws IOException
    {

        BufferedReader br=new BufferedReader(new InputStreamReader(System.in));
        Scanner sc=new Scanner(System.in);
        int n=sc.nextInt();

        String a[]=new String[n];

        for(int i=0;i<n;i++){
            System.out.println("Enter the String");
            a[i]=br.readLine();
        }

        System.out.println("Enter the String to search");
        String x=br.readLine();
        int b=0;
        
        for(int i=0;i<n;i++){
          
            if(a[i].equals(x)){
                String t=a[b];
                a[b]=a[i];
                a[i]=t;
                b++;
            }
            else
            {
               int z=i;
               String y=a[z];
               for(int j=i;j<n-1;j++){
               a[z]=a[++z];
            }
            a[n-1]=y;
            }
          
        }
        for(int i=0;i<n;i++){
            System.out.print(a[i]+"\t");
        }
    }
}
