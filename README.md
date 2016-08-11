# Java-linked-list
Create a singly linked list in Java



import java.io.*;
import java.util.Scanner;

public class SingleLinkedList {

	
	
	public class Node {

		 private int data;
		 private Node next;
		
		public Node() //constructor with no parameters
		{
			data = 0;
			next = null;
		}
		
		public Node(int i)//one argument constructor
		{
			data = i;
			next = null;
		}

	}
	
	private Node head; //first node of linked list
	
	
	public SingleLinkedList() throws IOException //program that reads file and puts int values into a linked list
	{
		
		Scanner inputFile = new Scanner(new File("C:\\Users\\Scott\\Desktop\\in.txt"));
		int input;
		Node a,b;
		int FirstInput = inputFile.nextInt();//initializes first input int from file
		System.out.println("first input is " +FirstInput);//prints this value to help me see what is going into the list
		
	
		
		//create the first node
		head = new Node(FirstInput);//head references the first node in the linked list
		a = head; //head and are both a reference to the first node
		
		//System.out.println("first node contains " + FirstInput);//helps me verify what is in the first node

		
		//add links to Linked list from file
		while (inputFile.hasNextInt())
		{	
			input = inputFile.nextInt();
			b = new Node(input);
			a.next = b;
			a = b;
			
			//System.out.println("next node contains " + input);//helps me verify what is in these nodes

		}
			
		inputFile.close();
	}
	
	public void PrintListSumAndEval()
	{
		
		
		int countertotal = 0;
		int sumtotal = 0;
		Node a =head;
		
		for(Node p = head; p != null; p = p.next ){//first node "p" is the head, while p has a value, move to next node
		       
			System.out.println(p.data);//prints data in each node
			sumtotal += p.data;//keeps a running sum of the data--i'm practicing doing a calculation on the linked list
			countertotal++;// counter variable to keep track of the number of links in the list
			
		
			}
		System.out.println("sum = "+sumtotal);//prints the sum
		System.out.println("counter = "+countertotal);
	}
		
				
		
	
	public static void main(String[] args) throws IOException 
	{
		SingleLinkedList MyIntegerList = new SingleLinkedList(); //create the linked list
		MyIntegerList.PrintListSumAndEval(); //test and evaluate the linked list
		
	}

}
