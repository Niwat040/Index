public class Index {

    public static int findZeroIndex(int[] a, int[] b) {
        int left = 0;
        int right = b.length - 1;
    
        while (left <= right) {
          int sum = left + (right - left) / 2;
    
          if (b[sum] == 0) {
            if (sum == 0 || b[sum - 1] != 0) {
              return sum;
            } else {
              right = sum - 1;
            }
          } else if (b[sum] < 0) {
            left = sum + 1;
          } else {
            right = sum - 1;
          }
        }
    
        return -1; 
      }
    
      public static void main(String[] args) {
        int[] a = {1, 3, 4, 6, 7, 8, 9, 20};
        int[] b = {1, 3, 0, 4, 6, 7, 8, 9, 20};
    
        int in = findZeroIndex(a, b);
    
        if (in != -1) {
          System.out.println("ดัชนีของ 0 ใน a2: " + in);
        } else {
          System.out.println("ไม่พบ 0 ใน a2");
        }
      }
}
