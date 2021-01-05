# mygit
#include<iostream>
#include<algorithm>
#include<vector>
using namespace std;
 
bool desc(int a,int b)
{
    return a>b;
}
/*이 방법은 숫자가 커지면 시간 초과 */
/*
int main()
{
    int n,m,k;
    cin>>n>>m>>k;
    int arr[1000]={0,};
    
    for(int i=0;i<n;i++)
    {
        cin>>arr[i];
    }
    sort(arr,arr+n,desc);
    
    for(int i=0;i<n;i++)
        cout<<arr[i]<<' ';
    int sum=0;
    
    while(1){
         if(m==0)
        break;
        for(int i=0;i<k;i++)
        {
         sum+=arr[0];
         m--;   
          }
         sum+=arr[1];
          m--;
    }
    
    cout<<sum<<'\n';
    
}*/

int main()
{
    int n,m,k;
    cin>>n>>m>>k;
    vector<int>v;
    
    for(int i=0;i<n;i++)
    {
        int a;
        cin>>a;
        v.push_back(a);
    }
     sort(v.begin(), v.end()); 
    int fbig=v[n-1];
    int sbig=v[n-2];
    
    int fbigcnt=(m/(k+1))*k;
    fbigcnt+=m%(k+1);
    int result=0;
    
    result+=fbigcnt*fbig;
    result+=(m-fbigcnt)*sbig;
    
    cout<<result<<'\n';
}
