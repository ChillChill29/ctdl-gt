```
> #h1
> #h2
> ...
> *in đậm*
> **bôi đậm*
> ***in nghiêng và bôi đậm***
> `thêm code`
> [title](link//anh)
> gạch đầu dòng:
	> *
	> *
	> *
	> hoặc
	> 1.
	> 2.
	> 3.
> gạch kẻ ***
> highlight text >
> \
> {@youtube: Youtube ID or url}
```

## Các lý thuyết tổng hợp

**Độ phức tạp** là gì?
> Độ phức tạp thuật toán là định lượng tương đối thể hiện **số phép toán** của giải thuật so với kích thước của đầu vào.

**Độ ổn định(stable)** là gì?
> Độ ổn định của thuật toán là **đảm bảo thứ tự ban đầu** của dữ liệu đầu vào sau khi sắp xếp

![Tổng hợp độ phức tạp](./image/comparison.jpg)

Phân loại dựa trên **phương pháp**

* Cách tiếp cận ***chia để trị***: merge sort và quicksort
* Cách tiếp cận gia tăng việc sử dụng các ***vòng lặp lồng nhau***:  bucket sort, selection sort, insertion sort.
* Giải quyết vấn đề bằng cách sử dụng ***cấu trúc dữ liệu***: heapsort, tree sort
* Giải quyết vấn đề bằng cách sử dụng ***băm***: counting sort

![Thời gian sắp xếp](./image/timeChange.gif)

***
## Giải thuật sắp xếp selectionsort
####1. Lý thuyết
> **Sắp xếp chọn** được tiến hành bằng cách **chia mảng thành hai phần**, **được sắp xếp** ở phía bên phải, và **chưa được sắp xếp** ở phía bên trái. 

> Sau mỗi lần chạy, **phần tử lớn nhất(hoặc bé nhất)** luôn **được đẩy về phía mảng đã sắp xếp**

####2. Minh họa
![Minh họa selectionsort](./image/selectionSortExample.gif)
####3. Độ phức tạp
> Độ phức tạp thời gian của trường hợp **xấu nhất, trung bình và tốt nhất** đều là: **O (n * n)**. Vì giải thuật **luôn thực hiện quá trình lặp 2 mảng**.
####4. Code
```
> Thực hiện một vòng lặp tới vị trí gần cuối mảng(độ dài - 1)
> Đặt giá trị index vào vị trí đầu tiên của của lần lặp
> Thực hiện một vòng lặp từ vị trí tiếp theo đến cuối mảng
> Đặt giá trị index nếu giá trị hiện tại lớn hơn giá trị tại index
> Đảo nếu vị trí index và vị trí đầu tiên của lần lặp
```
```
void selectionSort(int arr[], int n)
{
    int i, j, min_idx;
    for (i = 0; i < n-1; i++)
	    min_idx = i;
	    for (j = i+1; j < n; j++)
	        if (arr[j] < arr[min_idx])
	        min_idx = j;
		swap(arr[min_idx], arr[i]);
}
```

***

## Giải thuật sắp xếp bubblesort
####1. Lý thuyết
> **Sắp xếp nổi bọt** được tiến hành dựa trên việc **so sánh cặp phần tử liền kề nhau và tráo đổi thứ tự** nếu chúng không theo thứ tự.

> Sau mỗi lần chạy, **phần tử lớn nhất luôn nổi lên trên tuần tự**.

####2. Minh họa

![minh họa bubblesort](./image/bubbleSortExample.gif)

####3. Độ phức tạp
> Độ phức tạp thời gian của trường hợp **tốt nhất và trung bình**: **O (n * n)**. Trường hợp xấu nhất xảy ra **khi mảng được sắp xếp ngược lại**.

> Độ phức tạp về thời gian của trường hợp ***tốt nhất***: **O (n)**. Trường hợp tốt nhất xảy ra **khi mảng đã được sắp xếp**.

####4. Code
* thuật toán cơ bản
```
* Thực hiện một vòng lặp từ đầu đến cuối mảng
* Thực hiện một vòng lặp từ đầu đến vị trí i(độ dài - số vòng lặp)
* Thực hiện đảo phần tử nếu phần tử trước lớn hơn phần tử sau
```
```
void bubbleSort(int arr[], int lengthOfArr)  
{  
    int i, j;  
    for (i = 0; i < lengthOfArr-1; i++)
	    // Last i elements are already in place  
	    for (j = 0; j < lengthOfArr-i-1; j++)  
	        if (arr[j] > arr[j+1])  
	            swap(&arr[j], &arr[j+1]);  
} 
```
* thuật toán cải tiến
> Có thêm **biến bool kiểm tra**, nếu mảng đã tối ưu và **không xảy ra sự thay đổi** nào thì trực tiếp **ngắt ngay lần chạy thứ nhất**
```
void bubbleSort(int arr[], int n) 
{ 
   int i, j; 
   bool swapped; 
   for (i = 0; i < n-1; i++) 
   { 
     swapped = false; 
     for (j = 0; j < n-i-1; j++) 
     { 
        if (arr[j] > arr[j+1]) 
        { 
           swap(&arr[j], &arr[j+1]); 
           swapped = true; 
        } 
     }
     if (swapped == false) 
        break; 
   } 
}
```
## Giải thuật sắp xếp insertionsort
####1. Lý thuyết

####2. Minh họa
####3. Độ phức tạp
####4. Code
## giải thuật sắp xếp quicksort
####1. Lý thuyết
####2. Minh họa
####3. Độ phức tạp
####4. Code
## giải thuật sắp xếp heap heapsort 
####1. Lý thuyết
####2. Minh họa
####3. Độ phức tạp
####4. Code
## giải thuật sắp xếp trộn merge sort
####1. Lý thuyết
####2. Minh họa
####3. Độ phức tạp
####4. Code
## bài toán sắp xếp và tìm kiếm tuần tự, tìm kiếm nhị phân
####1. Lý thuyết
####2. Minh họa
####3. Độ phức tạp
####4. Code
## cây nhị phân tìm kiếm
####1. Lý thuyết
####2. Minh họa
####3. Độ phức tạp
####4. Code

***
##Đọc thêm
***
## cấu trúc dữ liệu biểu diễn danh sách(ngăn xếp và hàng đợi)
####1. Lý thuyết
####2. Minh họa
####3. Độ phức tạp
####4. Code
## cây nhị phân và ứng dụng
####1. Lý thuyết
####2. Minh họa
####3. Độ phức tạp
####4. Code
## giải thuật sắp xếp shellsort
####1. Lý thuyết
####2. Minh họa
####3. Độ phức tạp
####4. Code
## giải thuật sắp xếp bằng cơ chế radix sort
####1. Lý thuyết
####2. Minh họa
####3. Độ phức tạp
####4. Code
## cây tìm kiếm cơ số radix search tree
####1. Lý thuyết
####2. Minh họa
####3. Độ phức tạp
####4. Code
## cây tìm kiếm số học digtal search tree
####1. Lý thuyết
####2. Minh họa
####3. Độ phức tạp
####4. Code
