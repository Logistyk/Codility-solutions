# Codility-solutions_BinaryGap

import java.util.*;

class Solution {
    public int solution(int N) {
        String binary = Integer.toBinaryString(N);
        int counter = 0;
        int longest = 0;
        for(int i=1; i<binary.length(); i++){
            if(binary.charAt(i)=='0' && binary.charAt(i-1)=='1'){
                counter = 1;
            }else if(binary.charAt(i)=='0' && counter>0){
                counter++;
            }else if(binary.charAt(i)=='1' && binary.charAt(i-1)=='0'){
                if(longest<counter){
                    longest = counter;
                    counter = 0;
                }
            }
        }
        return longest;
    }
}
