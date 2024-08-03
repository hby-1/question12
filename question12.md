# 反转字符串

编写一个函数，其作用是将输入的字符串反转过来。输入字符串以字符数组 `s` 的形式给出。

不要给另外的数组分配额外的空间，你必须<span style="color:blue;font-weight:bold;">原地</span>**修改输入数组**、使用 O(1) 的额外空间解决这一问题。

## 示例 1：
>### 输入：
>s = ["h","e","l","l","o"]
>### 输出：
>["o","l","l","e","h"]

## 示例 2：
>### 输入：
>s = ["H","a","n","n","a","h"]
>### 输出：
>["h","a","n","n","a","H"]

## 代码：
1.

    public class Solution {
        public void ReverseString(char[] s) {
            int i=0;
            while(i<s.Length-1-i){
                s[i]=(char)(s[i]^s[s.Length-1-i]);
                s[s.Length-1-i]=(char)(s[i]^s[s.Length-1-i]);
                s[i]=(char)(s[i]^s[s.Length-1-i]);
                i++;
            }
        }
    }
2.

    public class Solution {
        public void ReverseString(char[] s) {
            int i=0;
            while(i<s.Length-1-i){
                (s[i],s[s.Length-1-i])=(s[s.Length-1-i],s[i]);
                i++;
            }
        }
    }
3.

    public class Solution {
        public void ReverseString(char[] s) {
            int i=0;
            while(i<s.Length-1-i){
                s[i]=(char)(s[i]+s[s.Length-1-i]);
                s[s.Length-1-i]=(char)(s[i]-s[s.Length-1-i]);
                s[i]=(char)(s[i]-s[s.Length-1-i]);
                i++;
            }
        }
    }
