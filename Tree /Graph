import java.util.Scanner;

//TIP To <b>Run</b> code, press <shortcut actionId="Run"/> or
// click the <icon src="AllIcons.Actions.Execute"/> icon in the gutter.
public class graphs {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter no of vertices");
        int n = sc.nextInt();

        while(n<0){
            System.out.println("enter valid vertex");
            n = sc.nextInt();
        }

        int[][]arr = new int[n][n];
        for ( int row=0;row<n;row++){
            for(int col=0;col<n;col++){
                System.out.println("Enter 1 if there is node between " +row+ "and" +col+ "else,Enter 0");
                int edge = sc.nextInt();
                if(edge!=0 && edge!=1){
                    edge = sc.nextInt();
                }
                arr[row][col] = edge;
                arr[col][row] = edge;


            }
        }
        System.out.println("Printing 2d matrix");

        for(int row=0;row<n;row++){
            for(int col=0;col<n;col++){
                System.out.print(arr[row][col]);
            }
        }
        }
    }
