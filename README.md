# findRatio
 public static double findRatio(int[] arr) {
        if (arr == null || arr.length < 4) {
            throw new IllegalArgumentException("Array must contain at least 4 elements");
        }

        int large1 = Integer.MIN_VALUE;//largest num
        int large2 = Integer.MIN_VALUE;//second largest num
        int small1 = Integer.MAX_VALUE;//smallest num
        int small2 = Integer.MAX_VALUE;//second smallest num

        for (int num : arr) {//iterate array to find largest and smallest num
            if (num > large1) {
                large2 = large1;
                large1 = num;
            } else if (num > large2) {
                large2 = num;
            }

            if (num < small1) {// update smallest numb if curr num is smaller
                small2 = small1;
                small1 = num;
            } else if (num < small2) {
                small2 = num;
            }
        }
        //calculate two largest/smallest num

        double ratio = (double)(large1 + large2) / (small1 + small2);
        return ratio;
    }

    public static void main(String[] args) {
        int[] arr = {4, 5, 16, 260, 2, 1, 7, 9, 17, 18, 96, 96, 145, 10, 74};
        //find ratio of array and print output
        double ratio = findRatio(arr);
        System.out.println("The Ratio is: " + ratio);
    }
}
