class Solution {
public:
    vector<int> majorityElement(vector<int>& nums) {
        int n=nums.size();
        int count=n/3;
        if(n==0){
            return nums;
            
        }
        vector<int> output;
        unordered_map<int,int> fr;
        for(int i=0;i<nums.size();i++){
            if(fr.count(nums[i])>0){
                fr[nums[i]]++;
                continue;
            }
            fr[nums[i]]=1;
        }
        unordered_map<int,int>::iterator it=fr.begin();
        while(it!=fr.end()){
            if(it->second>count){
                output.push_back(it->first);
            }
            it++;
            
        }
        return output;
        
    }
};
