# File-Handling
package com.example.filehandling;
import java.io.*;
import java.util.Scanner;
public class FileHandling {
	public static void main(String[] args)
	{
		System.out.println("Enter your choice:");
		System.out.println("1.create new file \n 2.Read file \n 3.Write file \n 4.Append file");
		Scanner sc=new Scanner(System.in);
		
		int n=sc.nextInt();
		
		switch(n)
		{
		case 1:if(n==1)
		       {
			   		try
			   		{
			   			File myobj=new File("C:\\users\\SaralaBesta\\Onedrive\\Desktop\\Akbar.txt");
			   			if(myobj.createNewFile())
			   			{
			   				System.out.printf("File is created",myobj.getName());
			   			}
			   			else
			   			{
			   				System.out.println("File already exists");
			   			}
			   		}
			   		catch(IOException e)
			   		{
			   			System.out.println("Error");
			   			e.printStackTrace();
			   		}
		       }
		break;
		case 2:if(n==2)
		{
			try
			{
				File myobj=new File("C:\\users\\SaralaBesta\\Onedrive\\Desktop\\Akbar.txt");
				Scanner reader=new Scanner(myobj);
				while(reader.hasNextLine())
				{
					String data=reader.nextLine();
					System.out.println(data);
				}
				reader.close();
			}
			catch(FileNotFoundException e)
			{
				System.out.println("Error");
				e.printStackTrace();
			}
		}
		break;
		case 3:if(n==3)
		{
			try
			{
				FileWriter myWriter=new FileWriter("C:\\users\\SaralaBesta\\Onedrive\\Desktop\\Akbar.txt");
				myWriter.write("Java has oops concepts.....");
				myWriter.close();
				System.out.println("Successfully wrote to the file....");
			}
			catch(IOException e)
			{
				System.out.println("Error");
				e.printStackTrace();
			}
		}
		break;
		case 4:if(n==4)
		{
			try
			{
				FileWriter myWriter=new FileWriter("C:\\users\\SaralaBesta\\Onedrive\\Desktop\\Akbar.txt");
				myWriter.write("Java is an object oriented language.");
				myWriter.close();
				System.out.println("successfully append to the file.");
			}
			catch(Exception e)
			{
				System.out.println("error");
			}
		}
		break;
		default:
			System.out.println("Invalid Operation");
			break;
			
			
		
	}

}
}
