import java.util.Scanner;

public class Main {
    static int MOD = 1000000007;

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        while (true) {
            int h = scanner.nextInt();
            if (h == 0) {
                break;
            }

            int[] values = new int[2 * h - 1];
            for (int i = 0; i < 2 * h - 1; i++) {
                values[i] = scanner.nextInt();
            }

            long result = maxPathSum(values, 0, h - 1);
            System.out.println(result % MOD);
        }
    }

    public static long maxPathSum(int[] values, int left, int right) {
        if (left == right) {
            // This is a leaf node
            return values[left];
        }

        int mid = (left + right) / 2;
        long leftSum = maxPathSum(values, left, mid);
        long rightSum = maxPathSum(values, mid + 1, right);

        // Calculate the maximum node value of the current node
        long maxSum = Math.max(leftSum, rightSum);
        if (left < mid) {
            maxSum = Math.max(maxSum, values[mid] * leftSum);
        }
        if (mid + 1 <= right) {
            maxSum = Math.max(maxSum, values[mid] * rightSum);
        }

        return maxSum;
    }
}
