1. Valid Palindrome :-

def isPalindrome(s):
    left=0
    right=len(s)-1
    while left<right:
        while left<right and not s[left].isalnum():
            left+=1
        while left<right and not s[right].isalnum():
            right-=1
        if s[left].lower()!=s[right].lower():
            return False
        left+=1
        right-=1
    return True

    

2. Reverse String :-

void reverseString(char* s, int sSize) {
    int left = 0;
    int right = sSize - 1;
    char temp;
    while (left<right) {
        temp=s[left];
        s[left]=s[right];
        s[right]=temp;
        left++;
        right--;
    }
}


3. Longest Common Prefix :-

class Solution:
    def longestCommonPrefix(self, strs):
        prefix = strs[0]
        for word in strs[1:]:
            while not word.startswith(prefix):
                prefix = prefix[:-1]
        return prefix
