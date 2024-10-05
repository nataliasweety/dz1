#include <iostream>

using namespace std;

int main()
{
   int arr[] = {64, 34, 25, 12, 22, 11, 90, 145, 11, 9, 38, 45, 93, 41};
   
   int n = sizeof(arr) / sizeof(arr[0]);
   int max;
   int pos_max;
   
   
   for (int i = 1; i <= n ;  i += 2) {
       max = arr[i-1];
       pos_max = i-1;
       
       if (arr[i] >= max) {
           max = arr[i];
           pos_max = i;
       }
       
       if (arr[i+1] >= max) {
           max = arr[i+1];
           pos_max = i+1;
       }
       
       if (pos_max != i) {
           arr[pos_max] = arr[i];
           arr[i] = max;
       }
       
   }
   
   cout << "Результат сортировки: ";
    for (int i=0; i<n; i++) {
        cout << arr[i] << " ";
    }
    return 0;
}
