# 2Darray2

1.Transpose of a matrix.
2.Transpose of a matrix in the same matrix.

3.Rotate the Square matrix by 90 degree clockwise.
-> First transpose and then reverse each row of the matrix.

4. Return n elements of the pascal triangle.
   ->package array;
import java.util.Scanner;

public class PascalTriangle {
    static void PrintMatrix(int[][] matrix, int n) {
        for (int i = 0; i < n; i++) {  // Loop starts from 0
            // Print spaces for alignment
            for (int j = 0; j < n - i - 1; j++) {
                System.out.print(" ");
            }
            // Print Pascal's triangle numbers
            for (int j = 0; j <= i; j++) {
                System.out.print(matrix[i][j] + " ");
            }
            System.out.println();
        }
    }

    static int[][] Pascal(int n) {
        int ans[][] = new int[n][];
        for (int i = 0; i < n; i++) {
            ans[i] = new int[i + 1];
            ans[i][0] = ans[i][i] = 1;
            for (int j = 1; j < i; j++) {
                ans[i][j] = ans[i - 1][j - 1] + ans[i - 1][j];
            }
        }
        return ans;
    }

    public static void main(String args[]) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter n: ");
        int n = sc.nextInt();
        sc.close();
        
        int ans2[][] = Pascal(n);
        PrintMatrix(ans2, n);
    }
}

