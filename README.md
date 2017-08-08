import java.io.*;
import java.util.*;
import java.text.*;
import java.math.*;
import java.util.regex.*;

public class Solution {

    public static void main(String[] args) {
        
         Scanner in = new Scanner(System.in);
        int n = in.nextInt();
        if(1<=n && n<=100000)
        {
        
        String[] arr = new String[n+1];
        String[][] ar = new String[n+1][4];       
        for (int i=0;i<n+1;i++) 
        {arr[i] = in.nextLine();}
       for(int k=1;k<n+1;k++)
       {
        ar[k]=arr[k].split(" "); 
       }
            
        int count = 0;  
       for(int j=1;j<n+1;j++)    
       {
        if(ar[j][0].equals("Q") == true)
            count++;
       }
       
                   
 int[] arry= new int[count];       
       
    int l = 0;   
     for(int t=n;t>0;t--)
     { 
        int c = 0;
      if (ar[t][0].equals("Q") == true)
      { 
        int d_end1 = 0;
          int c_id1 = 0;
          int r_id1 = 0;
        String[] q1 = ar[t][1].split(Pattern.quote(".")); 
        String[] q2 = ar[t][2].split(Pattern.quote("."));         
        String[] q3 = ar[t][3].split(Pattern.quote(".")); 
         
        int d_start1 = Integer.parseInt(q1[0]);
         try
         {
             d_end1 = Integer.parseInt(q1[1]);
         }
          
          catch(ArrayIndexOutOfBoundsException e)
          {
             d_end1 =0; 
          }
          
          int p_id1 = Integer.parseInt(q2[0]);
            try
         {
             c_id1 = Integer.parseInt(q2[1]);
         }
          
          catch(ArrayIndexOutOfBoundsException e)
          {
             c_id1 =0; 
          }
          
          int s_id1 = Integer.parseInt(q3[0]);
              
          try
         {
             r_id1 = Integer.parseInt(q3[1]);
         }
          
          catch(ArrayIndexOutOfBoundsException e)
          {
             r_id1 =0; 
          }
          
          
     for (int g=t-1;g>0;g--)
     {
       if (ar[g][0].equals("S") == true)
       
         
         {  
          int c_id = 0;
           int r_id = 0;
        String[] s1 = ar[g][1].split(Pattern.quote(".")); 
        String[] s2 = ar[g][2].split(Pattern.quote("."));         
        String[] s3 = ar[g][3].split(Pattern.quote(".")); 
         
        int d_start = Integer.parseInt(s1[0]);
         
          int p_id = Integer.parseInt(s2[0]);
            try
         {
             c_id = Integer.parseInt(s2[1]);
         }
          
          catch(ArrayIndexOutOfBoundsException e)
          {
             c_id =0; 
          }
          
          int s_id = Integer.parseInt(s3[0]);
              
          try
         {
             r_id = Integer.parseInt(s3[1]);
         }
          
          catch(ArrayIndexOutOfBoundsException e)
          {
             r_id =0; 
          }
         
             
 
         if((1<=d_start && d_start<=100 )&&((1<=d_start1 && d_start1<=d_end1 && 1<=d_end1 && d_end1<=100)||(1<=d_start1 && d_start1<=100 && d_end1 

==0 ))&&(1<=p_id && p_id<=10) && (0<=c_id && c_id<=4) && (1<=s_id && s_id<=7) && (0<=r_id && r_id<=25)&&((p_id1 == -1)||(1<=p_id1 && p_id1<=10)) && 

(0<=c_id1 && c_id1<=4) && ((s_id1 == -1)||(1<=s_id1 && s_id1<=7)) && (0<=r_id1 && r_id1<=25))         
  {
              
             if(((d_start1== d_start)&&(d_end1==0))||((d_start1<=d_start)&&(d_start<=d_end1)))
             {
if((c_id==0 && c_id1==0 && p_id1==p_id)||(c_id1==0 && p_id==p_id1 && c_id>0)||(p_id1==p_id && c_id1==c_id)||(p_id1==-1))
     {
if((r_id==0 && r_id1==0 && s_id1==s_id)||(r_id1==0 && s_id==s_id1 && r_id>0 )||(s_id1==s_id && r_id1==r_id)||(s_id1==-1))
{
 c++;   
}
     }
          }
             
 
  } 
       }
     
              }
       
       arry[l] = c;
       l++;
       /*System.out.println(c);*/  
      }    
          
             
         }
            
            
            for(int k=l-1;k>=0;k--)
            {System.out.println(arry[k]);  } 
            
            
            
        }
         
     }
        
        
            
        
    } 

