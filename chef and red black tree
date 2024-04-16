import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int Q = scanner.nextInt();
        scanner.nextLine();

        boolean invertColors = false;
        StringBuilder output = new StringBuilder();

        for (int i = 0; i < Q; i++) {
            String query = scanner.nextLine();
            String[] parts = query.split(" ");

            if (parts[0].equals("Qi")) {
                invertColors = !invertColors; // Toggle the inversion flag
            } else {
                int x = Integer.parseInt(parts[1]);
                int y = Integer.parseInt(parts[2]);

                int blackCount = countBlackNodes(x, y, invertColors);
                if (parts[0].equals("Qb")) {
                    output.append(blackCount).append("\n");
                } else if (parts[0].equals("Qr")) {
                    int totalCount = countNodesOnPath(x, y);
                    output.append(totalCount - blackCount).append("\n");
                }
            }
        }

        System.out.print(output.toString());
        scanner.close();
    }

    private static int countBlackNodes(int x, int y, boolean invertColors) {
        int blackCount = 0;
        while (x != y) {
            if (x > y) {
                blackCount += isBlack(x, invertColors) ? 1 : 0;
                x /= 2;
            } else {
                blackCount += isBlack(y, invertColors) ? 1 : 0;
                y /= 2;
            }
        }
        blackCount += isBlack(x, invertColors) ? 1 : 0; // Add the LCA (lowest common ancestor)
        return blackCount;
    }

    private static boolean isBlack(int node, boolean invertColors) {
        int depth = Integer.numberOfTrailingZeros(Integer.highestOneBit(node));
        boolean isNodeBlack = (depth % 2 == 0);
        return invertColors ? !isNodeBlack : isNodeBlack;
    }

    private static int countNodesOnPath(int x, int y) {
        int pathLength = 0;
        while (x != y) {
            if (x > y) {
                pathLength++;
                x /= 2;
            } else {
                pathLength++;
                y /= 2;
            }
        }
        pathLength++; // Count the LCA as well
        return pathLength;
    }
}
