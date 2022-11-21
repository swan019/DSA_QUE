#include <bits/stdc++.h> 
int first0(vector<int>& arr, int n, int k)
{
    int s = 0;
    int e = n - 1;
    int ans = -1;
    int mid = s + (e - s)/2;
    while(s <= e)
    {
        if(arr[mid] == k)
        {
            ans = mid;
            e = mid - 1;
        }else if(arr[mid] < k){
            s = mid + 1;
        }else{
            e = mid - 1;
        }
        
        mid = s + (e - s)/2;
    }
    
    return ans;
}

int last0(vector<int>& arr, int n, int k)
{
    int s = 0;
    int e = n - 1;
    int ans = -1;
    int mid = s + (e - s) / 2;
    while(s <= e)
    {
        if(arr[mid] == k)
        {
            ans = mid;
            s = mid + 1;
        }else if(arr[mid] < k)
        {
            s = mid + 1;
        }else{
            e = mid - 1;
        }
        
        mid = s + (e - s)/2;
    }
    
    return ans;
}
pair<int, int> firstAndLastPosition(vector<int>& arr, int n, int k)
{
    // Write your code here
    pair<int, int> res;
    res.first = first0(arr,n,k);
    res.second = last0(arr,n,k);
    
    return res;
}
