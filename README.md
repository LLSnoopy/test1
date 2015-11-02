# test1
test
public class QuickSort {
	static int partition(int[] a,int left,int right){
		int pivot = a[left];
		while(left<right){
			while(left<right && a[right]>=pivot){
				right--;
			}
			if(left<right){
				a[left++]=a[right];
			}
			while(left<right && a[left]<=pivot){
				left++;
			}
			if(left<right){
				a[right--]=a[left];
			}
		}
		a[left]=pivot;
		return left;
	}
	
	static void quickSort(int[] a,int left,int right){
		int dp;
		if(left<right){
			dp=partition(a, left, right);
			quickSort(a, left, dp-1);
			quickSort(a, dp+1,right);
		}
	}
	
	public static void main(String[] args) {
		int[] a={5,3,2,6,8,5,3,6};
		System.out.println(Arrays.toString(a));
		QuickSort.quickSort(a, 0, a.length-1);
		System.out.println(Arrays.toString(a));
	}
}
