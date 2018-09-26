//Author: Eric
//Class		Computer Science Period 2
//Last Edited: Sept 7, 2018

import java.io.*;
import java.util.Random;
import java.util.Scanner;

class lab_3 {
	public static void main(String args[]) {

		//General
		int select = 0;
		//Quadratic
		double A = 0;
		double B = 0;
		double C = 0;
		double root_one = 0;
		double root_two = 0;
		double disc = 0;
		double sqrt_v = 0;
		double sqrt_v2 = 0;
		//Pythagorean Theorem
		double opposite = 0;
		double adjacent = 0;
		double hyp = 0;
		double output = 0;
		double set_a = 0;
		double set_b = 0;
		double set_c = 0;
		double tan = 0;
		double cos = 0;
		double sin = 0;

		do {
			Scanner in = new Scanner (System.in);

			System.out.println("Selectable programs:");
			System.out.println("     ");
			System.out.println("0: End Program:");
			System.out.println("1: Quadratic:");
			System.out.println("2: Pythagorean Theorem:");
			System.out.println("     ");
			System.out.print("Select a program to run: ");

			select = in.nextInt();

			if (select == 1) {
				System.out.println("Enter the three values below; A, B, and C, to find the roots of this equation");
				System.out.println("         ");
				System.out.print("Enter the value for A: ");

				A = in.nextDouble();

				System.out.print("Enter you value for B: ");

				B = in.nextDouble();

				System.out.print("Enter your value for C: ");

				C = in.nextDouble();

				disc = (Math.pow(B,2)) - (4 * A *C);

				sqrt_v = Math.pow(disc,2);

				sqrt_v2 = Math.sqrt(Math.sqrt(sqrt_v));

				if (disc > 0) {

					root_one = (-B + Math.sqrt(Math.pow(B, 2) - (4*A*C))) / (2*A);
					root_two = (-B - Math.sqrt(Math.pow(B, 2) - (4*A*C))) / (2*A);

					System.out.println("The roots are real and unequal. Root one is: "+root_one+ ". The second root is: "+root_two);

				} else if (disc == 0) {

					root_one = (-B + Math.sqrt(Math.pow(B, 2) - (4*A*C))) / (2*A);

					System.out.println("This quadratic has a double root. The root is: "+root_one);

				} else {

					root_one = (-B + Math.sqrt(Math.pow(B, 2) - (4*A*C))) / (2*A);
					root_two = (-B - Math.sqrt(Math.pow(B, 2) - (4*A*C))) / (2*A);

					System.out.println("Your roots are imaginary, they are: "+ -B / (2 * A)+ " + i" +sqrt_v2+ " and "+ -B / (2 * A)+ " - i"+sqrt_v2);

				}
			} else if (select == 2) {
				System.out.println("Enter two of the three sides for a missing triangle, and the program will calculate the missing side for you.");
				System.out.println("Note: For the program to work you need to enter '-1' into the missing side.");

				System.out.print("Insert the opposite side of the triangle: ");

				opposite = in.nextDouble();

				System.out.print("Insert the adjacent side of the triangle: ");

				adjacent = in.nextDouble();

				System.out.print("Insert the hypotenuse of the triangle: ");

				hyp = in.nextDouble();

				if (opposite == -1) {
					set_a = (hyp * hyp) - (adjacent * adjacent);

					output = Math.sqrt(set_a);
					tan = Math.atan(output/adjacent);
					cos = Math.acos(adjacent/hyp);
					sin = Math.asin(output/hyp);

					System.out.println("The missing side of the triangle is " +output);
					System.out.println("The tangent is: "+tan);
					System.out.println("The cosine is: "+cos);
					System.out.println("The sine is: "+sin);
				} else if (adjacent == -1) {
					set_b = (hyp * hyp) - (opposite * opposite);

					output = Math.sqrt(set_b);
					tan = Math.atan(opposite/output);
					cos = Math.acos(output/hyp);
					sin = Math.asin(opposite/hyp);

					System.out.println("The missing side of the triangle is " +output);
					System.out.println("The tangent is: "+tan);
					System.out.println("The cosine is: "+cos);
					System.out.println("The sine is: "+sin);
				} else if (hyp == -1) {
					set_c = (opposite * opposite) + (adjacent * adjacent);

					output = Math.sqrt(set_c);
					tan = Math.atan(opposite/adjacent);
					cos = Math.acos(adjacent/output);
					sin = Math.asin(opposite/output);

					System.out.println("The missing side of is "+output);
					System.out.println("The tangent is: "+tan);
					System.out.println("The cosine is: "+cos);
					System.out.println("The sine is: "+sin);
				}
			}
		} while (select != 0);

		System.out.println("Program ended");
	}
}