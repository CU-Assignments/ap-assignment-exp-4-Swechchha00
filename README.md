# experiment-no.-4-22BCS_IOT-701B
https://leetcode.com/problems/longest-nice-substring/description/
class Solution {
public:
    string longestNiceSubstring(string s) {
        if (s.size() < 2) return ""; 
        unordered_set<char> charSet(s.begin(), s.end()); 
        for (int i = 0; i < s.size(); i++) {
            if (charSet.count(tolower(s[i])) && charSet.count(toupper(s[i]))) {
                continue;
            }
            // Split at this character and solve recursively
            string left = longestNiceSubstring(s.substr(0, i));
            string right = longestNiceSubstring(s.substr(i + 1));
            return left.size() >= right.size() ? left : right;
        } 
        return s;
    }
};

https://leetcode.com/problems/maximum-subarray/description/
Experiment no. 4
class Solution {
public:
    int maxSubArray(vector<int>& nums) {
        int maxSum = nums[0]; // Initialize maxSum with the first element
        int currentSum = nums[0]; // Initialize current sum
        for (int i = 1; i < nums.size(); i++) {
            currentSum = max(nums[i], currentSum + nums[i]); // Extend or restart the subarray
            maxSum = max(maxSum, currentSum); // Update maxSum if currentSum is greater
        }
        return maxSum;
    }
};

