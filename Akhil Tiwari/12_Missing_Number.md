
**Method1:**
class Solution {
public:
    int missingNumber(vector<int>& nums) 
    {
        int t=nums.size();
        int tsum=(t*(t+1))/2;
        cout<<tsum;
        int msum=0;
        for(int i=0;i<nums.size();i++)
        {
            msum=msum+nums[i];
        }
         tsum=tsum-msum;
        if(tsum==0)return 0;
        else return tsum;
    }
};   
                                       
**************************************************************************************************************************        
**Method2**
class Solution {
public:
    int missingNumber(vector<int>& nums) 
    {
     map<int,int>mis;
        for(int i=0;i<=nums.size();i++)
        {
            mis[i]++;
        }
        map<int,int>::iterator it;
        for(int i=0;i<nums.size();i++)
        {
            mis[nums[i]]++;
        }
          for(it=mis.begin();it!=mis.end();it++)
        {    
            if(it->second!=2){return it->first; }
        }
        return 0;
    }
};
